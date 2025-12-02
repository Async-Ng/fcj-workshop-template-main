---
title: "Kiến trúc chi tiết"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 5.3.1. </b> "
---

Hãy cùng tìm hiểu source code **BackendStack** để hiểu cách hệ thống hoạt động. Dưới đây là các đoạn code chi tiết cho từng tài nguyên.

#### 1. Cơ sở dữ liệu (Amazon DynamoDB)

Chúng ta khởi tạo 7 bảng DynamoDB sử dụng chế độ `PAY_PER_REQUEST` (On-Demand) để tối ưu chi phí và khả năng mở rộng.

```typescript
// 1. Listings Table (Room rentals)
const listingsTable = new dynamodb.Table(this, "ListingsTable", {
  tableName: "BoardingHouseListings",
  partitionKey: { name: "listingId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});

// 2. User Profiles Table
const userProfilesTable = new dynamodb.Table(this, "UserProfilesTable", {
  tableName: "UserProfiles",
  partitionKey: { name: "userId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});

// 3. OTP Table (Phone Verification) - Auto-delete after 5 mins (TTL)
const otpTable = new dynamodb.Table(this, "OTPVerifications", {
  tableName: "OTPVerifications",
  partitionKey: {
    name: "phoneNumber",
    type: dynamodb.AttributeType.STRING,
  },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  timeToLiveAttribute: "ttl", // TTL configuration
  removalPolicy: RemovalPolicy.DESTROY,
});

// 4. Favorites Table - Includes Sort Key for quick lookup by user
const favoritesTable = new dynamodb.Table(this, "FavoritesTable", {
  tableName: "UserFavorites",
  partitionKey: { name: "userId", type: dynamodb.AttributeType.STRING },
  sortKey: { name: "listingId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});

// 5. Support Requests Table
const supportRequestsTable = new dynamodb.Table(this, "SupportRequestsTable", {
  tableName: "SupportRequests",
  partitionKey: {
    name: "requestId",
    type: dynamodb.AttributeType.STRING,
  },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});

// 6. Search History Table - Includes TTL
const searchHistoryTable = new dynamodb.Table(this, "SearchHistoryTable", {
  tableName: "SearchHistory",
  partitionKey: { name: "userId", type: dynamodb.AttributeType.STRING },
  sortKey: { name: "searchId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  timeToLiveAttribute: "ttl",
  removalPolicy: RemovalPolicy.DESTROY,
});

// 7. User Preferences Table
const userPreferencesTable = new dynamodb.Table(this, "UserPreferencesTable", {
  tableName: "UserPreferences",
  partitionKey: { name: "userId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});
```

#### 2. Lưu trữ (Amazon S3)

Bucket S3 được tạo để lưu trữ hình ảnh phòng, được cấu hình với bảo mật chặn truy cập công khai và tự động xóa khi stack bị hủy.

```typescript
const imagesBucket = new s3.Bucket(this, "BoardingHouseImages", {
  bucketName: `findnest-images-${cdk.Aws.ACCOUNT_ID}`, // Unique bucket name
  removalPolicy: RemovalPolicy.DESTROY,
  autoDeleteObjects: true,
  blockPublicAccess: s3.BlockPublicAccess.BLOCK_ALL, // Private by default
});
```

#### 3. Xác thực (Amazon Cognito)

Chúng ta cấu hình User Pool để quản lý người dùng và Identity Pool để cấp quyền truy cập trực tiếp từ Frontend đến các tài nguyên AWS.

```typescript
// Create User Pool
const userPool = new cognito.UserPool(this, "UserPool", {
  userPoolName: "FindNestUsers",
  selfSignUpEnabled: false, // User created via API (Backend trigger)
  signInAliases: {
    phone: true, // User uses Phone Number
    username: true, // Admin uses Username
  },
  autoVerify: { phone: true },
  standardAttributes: {
    email: { required: false, mutable: true },
    phoneNumber: { required: false, mutable: true },
  },
  passwordPolicy: {
    minLength: 8,
    requireLowercase: true,
    requireUppercase: true,
    requireDigits: true,
    requireSymbols: true,
  },
  accountRecovery: cognito.AccountRecovery.PHONE_ONLY_WITHOUT_MFA,
  removalPolicy: RemovalPolicy.DESTROY,
});

// Create Client App
const userPoolClient = userPool.addClient("UserPoolClient", {
  authFlows: {
    userPassword: true,
    adminUserPassword: true, // Used for Backend auth flow
    custom: true,
  },
});

// User Groups
const usersGroup = new cognito.CfnUserPoolGroup(this, "UsersGroup", {
  userPoolId: userPool.userPoolId,
  groupName: "Users",
});

const landlordsGroup = new cognito.CfnUserPoolGroup(this, "LandlordsGroup", {
  userPoolId: userPool.userPoolId,
  groupName: "Landlords",
});

const adminsGroup = new cognito.CfnUserPoolGroup(this, "AdminsGroup", {
  userPoolId: userPool.userPoolId,
  groupName: "Admins",
});

// Identity Pool for Frontend
const identityPool = new cognito.CfnIdentityPool(this, "IdentityPool", {
  identityPoolName: "FindNestMapAccess",
  allowUnauthenticatedIdentities: true, // Allow guests to view map
  cognitoIdentityProviders: [
    {
      clientId: userPoolClient.userPoolClientId,
      providerName: userPool.userPoolProviderName,
    },
  ],
});
```

#### 4. Dịch vụ Vị trí (Maps & Geocoding)

Khởi tạo tài nguyên Location Service sử dụng Esri data provider.

```typescript
const placeIndex = new location.CfnPlaceIndex(this, "PlaceIndex", {
  indexName: "FindNestPlaces",
  dataSource: "Esri",
});

const map = new location.CfnMap(this, "Map", {
  mapName: "FindNestMap",
  configuration: { style: "VectorEsriStreets" },
});

const routeCalculator = new location.CfnRouteCalculator(
  this,
  "RouteCalculator",
  {
    calculatorName: "FindNestRoutes",
    dataSource: "Esri",
  }
);
```

#### 5. Compute (AWS Lambda Monolith)

Cấu hình Lambda Function chứa toàn bộ logic Backend, bao gồm injection đầy đủ các biến môi trường.

```typescript
const apiLambda = new lambda.Function(this, "ApiLambda", {
  functionName: "FindNestApi",
  runtime: lambda.Runtime.NODEJS_20_X,
  handler: "index.handler",
  code: lambda.Code.fromAsset(path.join(__dirname, "../../backend/src/lambda")),
  timeout: cdk.Duration.seconds(30),
  logGroup: logGroup,
  environment: {
    // Environment variables connecting resources
    LISTINGS_TABLE_NAME: listingsTable.tableName,
    USER_PROFILES_TABLE_NAME: userProfilesTable.tableName,
    OTP_TABLE_NAME: otpTable.tableName,
    FAVORITES_TABLE_NAME: favoritesTable.tableName,
    SUPPORT_REQUESTS_TABLE_NAME: supportRequestsTable.tableName,
    SEARCH_HISTORY_TABLE_NAME: searchHistoryTable.tableName,
    USER_PREFERENCES_TABLE_NAME: userPreferencesTable.tableName,
    IMAGES_BUCKET_NAME: imagesBucket.bucketName,
    USER_POOL_ID: userPool.userPoolId,
    USER_POOL_CLIENT_ID: userPoolClient.userPoolClientId,
    PLACE_INDEX_NAME: placeIndex.indexName,
    MAP_NAME: map.mapName,
    ROUTE_CALCULATOR_NAME: routeCalculator.calculatorName,
    BEDROCK_MODEL_ID: "anthropic.claude-3-sonnet-20240229-v1:0",
    REGION: cdk.Aws.REGION,
  },
});
```

#### 6. Quyền hạn (Granular Access Control)

Chúng ta cấp **quyền chi tiết** cho Lambda Function. Dưới đây là danh sách đầy đủ các quyền được cấp:

**A. Quyền đọc/ghi vào Database và S3:**

```typescript
listingsTable.grantReadWriteData(apiLambda);
userProfilesTable.grantReadWriteData(apiLambda);
otpTable.grantReadWriteData(apiLambda);
favoritesTable.grantReadWriteData(apiLambda);
supportRequestsTable.grantReadWriteData(apiLambda);
searchHistoryTable.grantReadWriteData(apiLambda);
userPreferencesTable.grantReadWriteData(apiLambda);
imagesBucket.grantReadWrite(apiLambda);
```

**B. Quản lý người dùng trong Cognito (Full Admin Actions):**

```typescript
apiLambda.addToRolePolicy(
  new iam.PolicyStatement({
    actions: [
      "cognito-idp:AdminCreateUser",
      "cognito-idp:AdminSetUserPassword",
      "cognito-idp:AdminInitiateAuth",
      "cognito-idp:AdminGetUser",
      "cognito-idp:AdminAddUserToGroup",
      "cognito-idp:AdminRemoveUserFromGroup",
      "cognito-idp:AdminListGroupsForUser",
      "cognito-idp:AdminUpdateUserAttributes",
      "cognito-idp:AdminEnableUser",
      "cognito-idp:AdminDisableUser",
      "cognito-idp:AdminDeleteUser",
      "cognito-idp:ListUsers",
      "cognito-idp:GlobalSignOut",
    ],
    resources: [userPool.userPoolArn],
  })
);
```

**C. Tích hợp với các dịch vụ khác (SNS, Bedrock, Location):**

```typescript
// Send SMS (OTP)
apiLambda.addToRolePolicy(
  new iam.PolicyStatement({
    actions: ["sns:Publish"],
    resources: ["*"],
  })
);

// Invoke AI (Claude 3)
apiLambda.addToRolePolicy(
  new iam.PolicyStatement({
    actions: ["bedrock:InvokeModel"],
    resources: ["arn:aws:bedrock:*::foundation-model/anthropic.claude-3-*"],
  })
);

// Access Location Service
apiLambda.addToRolePolicy(
  new iam.PolicyStatement({
    actions: [
      "geo:SearchPlaceIndexForText",
      "geo:GetPlace",
      "geo:CalculateRoute",
      "geo:SearchPlaceIndexForPosition",
    ],
    resources: [placeIndex.attrArn, routeCalculator.attrArn],
  })
);
```

#### 7. API Gateway (REST API)

Tạo Endpoint công khai để client có thể gọi Lambda function.

```typescript
const api = new apigateway.LambdaRestApi(this, "BoardingHouseApi", {
  handler: apiLambda,
  proxy: true,
  deployOptions: {
    stageName: "prod",
    throttlingBurstLimit: 100,
    throttlingRateLimit: 50,
  },
  defaultCorsPreflightOptions: {
    allowOrigins: apigateway.Cors.ALL_ORIGINS,
    allowMethods: apigateway.Cors.ALL_METHODS,
    allowHeaders: ["Content-Type", "Authorization"],
  },
  restApiName: "FindNestAPI",
});
```
