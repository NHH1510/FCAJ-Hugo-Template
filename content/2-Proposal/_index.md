---
title: "Proposal"
date : "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

### MUSIC STREAMING WEB

### 1. Executive Summary

This project focuses on building an online music streaming web system based on a serverless architecture using AWS services. The system allows users to access and stream music online, manage playlists, and supports artists and administrators in content management and platform operations. The solution is implemented using core AWS services such as Amazon S3 for media storage, DynamoDB for NoSQL data management, AWS Lambda for backend logic processing, API Gateway for request handling and routing, and Cognito for user authentication and authorization.

This architecture eliminates the need for managing traditional server infrastructure while providing automatic scalability and resource optimization based on demand. The serverless model not only ensures system performance and scalability but also optimizes operational costs, especially within the AWS Free Tier limits. In addition, the system is designed with a clear separation between frontend and backend, improving maintainability, scalability, and future integration capabilities. Overall, the project demonstrates the effective application of modern system design principles on cloud computing platforms, aiming to build a highly scalable, efficient, and practical web application.

---

### 2. Problem Statement

#### Current Problems

In the context of the increasing demand for sharing and accessing personal music content, existing platforms still do not fully meet user needs in terms of flexibility and personalization. Particularly for independent artists or general users, uploading and sharing personal music often faces multiple barriers such as complex processes, limited content control, and restricted audience reach.

Additionally, many current systems primarily focus on distributing content from major producers, making it difficult for independent or personal music products to gain wide exposure. This limits the growth and visibility opportunities for new artists and independent creators.

Moreover, content management and user interaction in existing platforms still have limitations, including lack of effective management tools, suboptimal scalability, and high operational costs as user numbers increase. Issues related to security, authentication, and content moderation also pose significant challenges in system development.

Therefore, it is necessary to build a web platform that allows users to easily upload, share, and manage personal music while ensuring performance, scalability, and cost efficiency. The system should support both general users and independent artists, creating an open, flexible, and accessible environment.

#### Proposed Solution

To address these challenges, the system is built based on a serverless architecture using core AWS services to ensure scalability, flexibility, and cost efficiency.

Specifically, Amazon S3 is used as the media storage platform for audio content, enabling fast and stable content retrieval through object storage mechanisms. System data, including user information, songs, and playlists, is stored in DynamoDB, which provides high scalability and flexibility for future expansion.

For business logic processing, AWS Lambda is used to implement backend functionalities, acting as an intermediary that receives user requests and returns responses via Lambda functions. To ensure security and user management, AWS Cognito is used for authentication and authorization, providing secure and efficient user registration, login, and session management.

The overall architecture is designed with a clear separation between storage, processing, and communication components, improving maintainability and scalability. Leveraging AWS managed services reduces infrastructure management overhead while benefiting from automatic scaling and high availability.

---

### 3. Solution Architecture

The system architecture is built on AWS Cloud using a serverless model, consisting of key components: content delivery, business logic processing, data storage, and user authentication. These components are organized into layers to ensure scalability, security, and performance.

![ConnectPrivate](/images/aws_architec.png)

- Users access the system via a domain managed by Route 53, combined with Certificate Manager to ensure secure HTTPS connections. Frontend content is distributed via CloudFront, improving access speed through CDN and caching.
- AWS WAF is integrated to protect against common attacks such as SQL Injection and DDoS. Static web content (frontend) is stored in S3 and delivered via CloudFront.
- Cognito handles authentication processes including Register, Login, and Refresh Token. API Gateway integrates an Authorizer to validate tokens before allowing access to backend services.
- Business logic is implemented through Lambda functions, organized into functional groups:
  - Lambda song services: handle song-related functionalities
  - Lambda user services: manage user information
  - Lambda artist services: handle artist data
  - Lambda account services: manage accounts and authentication
  - Lambda history services: store activity history
- API Gateway acts as an intermediary, receiving requests from clients and routing them to appropriate Lambda functions, enabling modular and scalable design.
- DynamoDB stores system metadata such as users, songs, playlists, and history.
- S3 Media stores audio files and images.
- CloudWatch monitors system activities, including logs from Lambda, API Gateway, and other services, supporting debugging and optimization.
- Amazon OpenSearch Service is a managed service for distributed search and analytics, based on Elasticsearch, enabling real-time data collection, storage, search, and analysis.

---

### 4. Technical Implementation

#### Implementation Phases

The project consists of two parts — frontend development and serverless backend development — each going through four phases:

*Research and architecture design:*  
Study AWS services (S3, DynamoDB, Lambda, API Gateway, Cognito, Amazon OpenSearch Service) and design a suitable serverless architecture for personal music sharing.

*Cost estimation and feasibility analysis:*  
Estimate AWS Free Tier usage, evaluate system operation with a small number of users, and adjust the design accordingly (Weeks 1–2).

*Architecture optimization:*  
Optimize Lambda usage, design DynamoDB using a query-first approach, reduce request volume, and optimize data flow between services (Weeks 2–3).

*Development, testing, deployment:*  
Build frontend, implement Lambda functions, configure API Gateway, and integrate Cognito. Then perform UI and functional testing before deploying the system to AWS (Weeks 3–7).

---

#### Technical Requirements

*Frontend (Client):*  
A web interface that allows users to stream music, manage content, and interact with the system. The frontend is deployed as a static website on S3 and distributed via CloudFront for performance optimization.

*Backend (Serverless):*

- AWS Lambda is used for business logic, including:
  - User management
  - Content management
  - Artist management
  - Activity history tracking
- API Gateway acts as the gateway to receive client requests and route them to Lambda.
- Amazon OpenSearch Service supports real-time data collection, storage, search, and analysis.

*Data Storage:*

- DynamoDB: stores metadata (users, songs, playlists, artists, history)
- S3: stores audio files and images

*Authentication and Authorization:*

- Cognito manages user registration, login, and access control
- API Gateway integrates Authorizer to validate tokens before processing requests

*Deployment and Tools:*

- AWS SAM for deploying Lambda and API Gateway
- GitHub for source code management
- HTTP/REST APIs for frontend-backend communication

---

### 5. AWS Cost Estimation (Free Tier Usage)

The system is designed using a serverless model and maximizes AWS Free Tier to minimize operational costs in the initial phase.

With a small user base and moderate traffic, estimated costs are:

- *AWS Lambda:*  
  Covered by Free Tier (1M requests/month, 400,000 GB-seconds) → ≈ 0 USD

- *Amazon API Gateway:*  
  Free Tier includes 1M requests/month → ≈ 0 USD

- *Amazon DynamoDB:*  
  Free Tier provides sufficient storage and capacity → ≈ 0 USD

- *Amazon S3:*  
  5GB free storage; additional cost if exceeded but remains low

- *Amazon Cognito:*  
  50,000 MAU free → suitable for small systems

- *CloudFront:*  
  1TB free data transfer/month → sufficient for basic streaming

- *Amazon OpenSearch Service:*  
  750 hours/month for small instances + 10GB storage → ≈ 0 USD

Total estimated cost in the initial phase is approximately *0 USD/month* within Free Tier limits. Costs scale with usage under the pay-as-you-go model.

---

### 6. Risk Assessment

Potential risks include:

- *Performance risks:*  
  Latency issues when user numbers grow if not optimized

- *Cost risks:*  
  Costs may increase rapidly beyond Free Tier limits

- *Security risks:*  
  Token, authorization, or unauthorized access issues if misconfigured

- *Data design risks:*  
  Poor DynamoDB design may lead to inefficient queries

- *Cloud dependency risks:*  
  Full dependency on AWS services

*Mitigation strategies:*

- Optimize data design and caching
- Set billing alerts
- Apply security best practices (IAM, Cognito)
- Monitor via CloudWatch

---

### 7. Expected Outcomes

After completion, the system is expected to:

- Successfully build a personal music sharing platform  
- Provide stable and scalable performance  
- Optimize operational costs  
- Ensure secure authentication and user management  
- Improve user experience with fast loading via CloudFront  
- Serve as a foundation for future features such as music recommendation, AI systems, and social features