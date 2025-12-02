---
title: "Workshop"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

# Building a Serverless Backend with AWS CDK

#### Overview

In this workshop, you will build a complete **Serverless Backend** for the **FindNest** application - a boarding house rental platform. You will use **AWS CDK (Cloud Development Kit)** to define and deploy your infrastructure as code.

You will learn how to:

- Deploy serverless infrastructure using AWS CDK with TypeScript
- Build RESTful APIs with API Gateway and Lambda
- Implement authentication with Amazon Cognito
- Store data in DynamoDB with proper data modeling
- Integrate AI capabilities with Amazon Bedrock (Claude 3)
- Add map functionality with Amazon Location Service
- Apply security best practices with IAM policies
- Manage infrastructure lifecycle (deploy and cleanup)

#### Architecture

You will deploy a modern serverless architecture consisting of:

- **API Gateway** - RESTful API endpoints
- **AWS Lambda** - Serverless compute (Node.js)
- **Amazon DynamoDB** - NoSQL database (7 tables)
- **Amazon Cognito** - User authentication and authorization
- **Amazon S3** - Image storage
- **Amazon Location Service** - Maps and geocoding
- **Amazon Bedrock** - AI/ML with Claude 3
- **Amazon SNS** - SMS notifications
- **CloudWatch Logs** - Monitoring and logging

#### Content

1. [Workshop Overview](5.1-Workshop-overview/)
2. [Prerequisites](5.2-Prerequiste/)
3. [Deploy Backend](5.3-DeployBackend/)
4. [Seeding Data](5.4-SeedingData/)
5. [System Validation](5.5-SystemValidation/)
6. [Clean Up Resources](5.6-Cleanup/)
