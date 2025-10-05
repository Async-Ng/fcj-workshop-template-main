---
title: "Proposal"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Smart Boarding House Finder

## AWS Serverless Recommendation Platform for Smart Accommodation Search

### 1. Executive Summary

The "Smart Boarding House Finder" platform addresses the challenge of manual, non-personalized accommodation search by integrating AI Recommendation and smart mapping based on OpenStreetMap. The web application (Frontend: React, Backend: AWS Lambda) stores data in S3, manages users via Cognito, and provides intelligent suggestions through TensorFlow.js or rule-based logic. Statistical dashboard utilizes AWS QuickSight for data visualization and insights.

### 2. Problem Statement

### What's the Problem?

Current platforms only support basic search by price, location, and area. Users still have to manually filter through hundreds of listings without personalized recommendations based on their income, lifestyle habits, or nearby amenities.

### The Solution

An intelligent boarding house search platform on AWS that recommends rooms based on income and lifestyle, displays nearby amenities via OpenStreetMap integration, automatically sends notifications when suitable rooms become available, and builds a serverless API using AWS Lambda for scalability and cost efficiency.

### Benefits and Return on Investment

The platform provides personalized search experience for students and workers seeking accommodation, helps landlords reach the right target customers, reduces time spent on manual filtering, and offers real-time notifications for new listings. Operating entirely within AWS Free Tier during MVP phase (~$0.5/month), the platform can scale to full AI Recommendation when sufficient data is collected, maintaining a smart suggestion experience without incurring costs in the initial stage.

### 3. Solution Architecture

The system utilizes AWS Serverless architecture and free open-source services to create a cost-effective and scalable platform.

| Component             | Service / Technology       |
| --------------------- | -------------------------- |
| Frontend Hosting      | AWS Amplify / CloudFront   |
| API Backend           | AWS Lambda + API Gateway   |
| Database              | DynamoDB                   |
| File Storage          | S3                         |
| User Management       | Cognito                    |
| Notifications         | AWS SES                    |
| Map & Location        | OpenStreetMap + Leaflet.js |
| Recommendation Engine | Rule-based + TensorFlow.js |
| Analytics & Dashboard | AWS QuickSight             |

![Smart Boarding House Finder Architecture](/images/2-Proposal/AWSProject.drawio.png)

### AWS Services Used

- **AWS Lambda**: Processes API requests and executes recommendation logic.
- **Amazon API Gateway**: Provides RESTful API endpoints for frontend communication.
- **Amazon DynamoDB**: Stores user profiles, room listings, and preferences.
- **Amazon S3**: Stores images and static assets.
- **AWS Amplify / CloudFront**: Hosts and delivers the React frontend application.
- **Amazon Cognito**: Manages user authentication and authorization.
- **AWS SES**: Sends email notifications for matching room listings.
- **AWS QuickSight**: Provides analytics dashboard for usage statistics.

### Component Design

- **Frontend Application**: React-based SPA hosted on AWS Amplify/CloudFront for responsive user interface.
- **API Layer**: AWS Lambda functions behind API Gateway handle business logic and data operations.
- **Database**: DynamoDB stores structured data with flexible schema for user and listing information.
- **Storage**: S3 buckets store room images and other static files with CloudFront CDN.
- **Recommendation Engine**: Rule-based logic in Lambda (MVP), with potential TensorFlow.js integration for client-side ML.
- **Map Integration**: OpenStreetMap with Leaflet.js displays location and nearby amenities.
- **Notification System**: AWS SES triggers email alerts when new matching listings are available.
- **User Management**: Amazon Cognito handles registration, login, and session management.

### 4. Technical Implementation

**Recommendation Engine Approach**

- **MVP Phase**: Rule-based logic processed in AWS Lambda (Node.js) based on user preferences, income range, and location filters.
- **Expansion Phase**: Integrate TensorFlow.js for client-side data processing and enhanced recommendation accuracy.
- **Advanced Phase**: Train ML models using Amazon Personalize when sufficient user data is collected.

**Technical Requirements**

- **Frontend**: React.js with responsive design, Leaflet.js for map integration, AWS Amplify SDK for backend communication.
- **Backend**: Node.js Lambda functions, AWS SDK for DynamoDB and S3 operations, API Gateway for RESTful endpoints.
- **Database**: DynamoDB tables for users, listings, preferences, and search history with appropriate indexes.
- **Storage**: S3 buckets with lifecycle policies for image optimization and cost management.
- **Authentication**: Cognito User Pools for secure user management with email verification.
- **Notifications**: SES templates for automated email alerts triggered by Lambda functions.

### 5. Timeline & Milestones

**Project Timeline**

- **Week 1-2**: Design AWS architecture and set up development environment.
- **Week 3-4**: Develop frontend interface and implement API endpoints.
- **Week 5**: Build and integrate AI Recommendation engine (rule-based MVP).
- **Week 6**: Testing, bug fixes, and demo preparation.
- **Post-Launch**: Monitor costs and performance, collect user feedback for improvements.

### 6. Budget Estimation

### Infrastructure Costs

| Component            | Service                    | Estimated Cost |
| -------------------- | -------------------------- | -------------- |
| Lambda + API Gateway | Backend                    | $0.10/month    |
| DynamoDB             | Database                   | $0.10/month    |
| S3 + CloudFront      | Storage                    | $0.20/month    |
| Cognito              | Authentication             | $0.05/month    |
| SES + QuickSight     | Notifications + Analytics  | $0.05/month    |
| Map & Location       | OpenStreetMap + Leaflet    | $0.00          |
| AI Engine            | Rule-based / TensorFlow.js | $0.00          |

**Total Estimated Cost**: ~$0.50/month (within AWS Free Tier)

**Note**: All services are designed to operate within AWS Free Tier limits during the MVP phase, with minimal costs for storage and data transfer.

### 7. Risk Assessment

#### Risk Matrix

- **Exceeding AWS Free Tier**: Medium impact, medium probability.
- **IAM or API Configuration Errors**: High impact, low probability.
- **Lack of Advanced AWS Skills**: Medium impact, medium probability.

#### Mitigation Strategies

- **Cost Management**: Implement AWS Budgets with alerts to monitor spending and prevent overages.
- **Security**: Configure IAM following the principle of least privilege with role-based access control.
- **Technical Complexity**: Start with rule-based AI in MVP phase to reduce training costs and complexity.

#### Contingency Plans

- **Budget Overrun**: Scale down to Free Tier services or pause non-essential features.
- **Technical Issues**: Maintain comprehensive documentation and use AWS CloudFormation for infrastructure rollback.
- **Performance Problems**: Implement caching strategies and optimize Lambda function execution time.

### 8. Expected Outcomes

#### Technical Improvements

- **MVP Launch**: Fully functional platform running entirely within AWS Free Tier.
- **Smart Recommendations**: Rule-based system providing personalized suggestions without AI training costs.
- **Scalability**: Architecture ready to integrate full AI Recommendation when sufficient data is collected.
- **User Experience**: Intuitive interface with real-time search and automated notifications.

#### Long-term Value

- **Data Collection**: Build user behavior dataset for future ML model training.
- **Platform Evolution**: Gradual transition from rule-based to AI-powered recommendations.
- **Cost Efficiency**: Maintain smart suggestion experience without incurring significant costs in initial stages.
- **Market Validation**: Proof of concept for intelligent accommodation search in Vietnam market.
