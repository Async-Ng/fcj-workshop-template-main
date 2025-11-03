---
title: "Week 6 Worklog"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

- Decompose the monolith into microservices and design bounded contexts.
- Implement serverless microservices and configure orchestration (CodeStar).
- Build scan/query and calculator microservices; expose and secure their APIs.
- Automate microservice deployment (CI/CD) and enable auto-release flows.
- Create and secure a Single Page Application with authentication (AAA) and trace its performance (X-Ray).
- Explore AWS AI services: Polly, Rekognition, and Lex integrations.

{{% notice warning %}}
AWS CodeStar has been discontinued. For reference only.
{{%/ notice %}}

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Start Date | Completion Date | Reference Material                                                              |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------------------------------------------- |
| Mon | - **Application Migrate Monolith:** <br>&emsp; + Test locally by Eclipse IDE <br>&emsp; + Deploy to ElasticBeanstalk <br>&emsp; + Update the application <br>&emsp; + Query the API use Eclipse IDE <br> - **Auto-release apps:** <br>&emsp; + Preparation <br>&emsp; + Configure automatic release <br>&emsp; + Application Deployment <br>&emsp; + Triển khai Windows Service sử dụng AWS CodeDeploy <br>&emsp; + Monitor your service                                                                                                                                                                                                                                                                  | 10/13/2025 |                 | <https://cloudjourney.awsstudygroup.com/4-modernize/>                           |
| Tue | - **Code authentication feature with Cognito:** <br>&emsp; + Configure Cognito User Pool <br>&emsp; + Implement sign-up flow <br>&emsp; + Implement sign-in flow <br>&emsp; + Configure app clients                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | 10/14/2025 | 10/14/2025      | <https://docs.aws.amazon.com/cognito/>                                          |
| Wed | - **Implement phone login with OTP using SNS:** <br>&emsp; + Configure SNS for SMS delivery <br>&emsp; + Integrate OTP generation <br>&emsp; + Implement OTP verification <br>&emsp; + Test phone authentication <br> - **Restructure UserProfile table in DynamoDB:** <br>&emsp; + Design new schema <br>&emsp; + Update access patterns <br>&emsp; + Add new attributes                                                                                                                                                                                                                                                                                                                                 | 10/15/2025 | 10/15/2025      | <https://docs.aws.amazon.com/sns/> <br> <https://docs.aws.amazon.com/dynamodb/> |
| Thu | - **Create a Microservice:** <br>&emsp; + Create a microservice <br>&emsp; + Expanding Serverless Microservices <br>&emsp; + Configure orchestration with CodeStar (reference-only — service discontinued) <br>&emsp; + Challenge - Expose microservice API <br> - **Data and workflow restructuring:** <br>&emsp; + Create A Scan & Query Microservice <br>&emsp; + Automate Your Microservice <br>&emsp; + Create an API For Your Microservice <br>&emsp; + Challenge - Enhance The TripSearch Microservice <br>&emsp; + Create A Calculator Microservice using AWS Step Functions <br>&emsp; + Challenge - Enhance The Calculator Service <br>&emsp; + Challenge - Implement An Image Manager Workflow | 10/16/2025 |                 | <https://cloudjourney.awsstudygroup.com/4-modernize/>                           |
| Fri | - **Create and authenticate Single Page Application:** <br>&emsp; + Creating A Single Page Application <br>&emsp; + Configure Authentication, Authorization and Accounting (AAA) <br>&emsp; + Tracing Application Performance With AWS X-Ray <br>&emsp; + Challenge <br> - **Experience AI services on AWS:** <br>&emsp; + Adding Speech Using Amazon Polly <br>&emsp; + Adding Object Recognition Using Amazon Rekognition <br>&emsp; + Adding A Chat Bot Using Amazon Lex <br>&emsp; + Challenge Exercises                                                                                                                                                                                              | 10/17/2025 |                 | <https://cloudjourney.awsstudygroup.com/4-modernize/>                           |

### Week 6 Achievements:

This week we progressed on modernizing the application and implementing several serverless capabilities. Key achievements aligned to the objectives:

- Monolith migration & release automation

  - Validated the monolith locally (Eclipse) and deployed a migration candidate to Elastic Beanstalk.
  - Configured an initial auto-release flow and prepared Windows Service deployment via AWS CodeDeploy.

- Authentication & security

  - Implemented Cognito-based user auth (sign-up/sign-in) and JWT validation.
  - Added phone-based OTP flows using SNS with rate limiting and verification.

- Data & microservices

  - Restructured the DynamoDB UserProfile schema to support new access patterns and migrations.
  - Created blueprints for Scan & Query and Calculator microservices; designed APIs and Step Functions workflows for the calculator.

- Microservice orchestration & CI/CD

  - Built a serverless microservice skeleton and planned orchestration with CodeStar.
  - Configured automated deployment steps for microservices and validated deployment flow.

- SPA and observability

  - Scaffolder for a Single Page Application prepared; configured authentication and AAA considerations and integrated X-Ray tracing for performance checks.

- AI experimentation
  - Integrated examples and demos for Amazon Polly, Rekognition and Lex to explore adding speech, object recognition, and chat bot features.
