

---

## 1. Development with AWS Services (≈32% — HIGHEST PRIORITY)

### Serverless & Compute

-  ** [[AWS Lambda]]**
    - [[AWS Lambda#1. Function Lifecycle & Handlers|1. Function Lifecycle & Handlers]] 
        
    - [[AWS Lambda#2. Resource Scaling (Memory vs. CPU)|2. Memory vs CPU scaling]]
        
    - [[AWS Lambda#3. Timeout & Environment Variables|3.Timeout & Environment Variables]]
        
    - Concurrency (reserved vs provisioned)
        
    - Event sources (S3, SQS, DynamoDB Streams, API Gateway)
        
    - Lambda Layers
        
    - VPC-enabled Lambda (cold start implications)
        
- **[[Amazon EC2]]**
    
    - User data
        
    - IAM role for EC2
        
    - Security groups vs NACLs (developer perspective)
        
- **[[AWS Elastic Beanstalk]]**
    
    - Deployment policies (all-at-once, rolling, blue/green)
        
    - Environment variables
        
    - When EB vs Lambda
        

---

### APIs & Integration

- **[[Amazon API Gateway]]**
    
    - REST API vs HTTP API
        
    - Lambda proxy integration
        
    - Mapping templates (VTL)
        
    - Authorization (IAM, Cognito, Lambda authorizer)
        
    - Throttling, caching, stages
        
- **[[AWS AppSync]]**
    
    - GraphQL basics
        
    - Data sources (Lambda, DynamoDB)
        

---

### Data Stores

- **[[Amazon DynamoDB]]**
    
    - Partition key vs sort key
        
    - Query vs Scan
        
    - Global vs Local Secondary Indexes
        
    - Read consistency (eventual vs strong)
        
    - Provisioned vs On-Demand capacity
        
    - DynamoDB Streams
        
    - TTL
        
    - DAX
        
- **[[Amazon S3]]**
    
    - Object vs bucket concepts
        
    - Versioning
        
    - Encryption (SSE-S3, SSE-KMS)
        
    - CORS
        
    - Pre-signed URLs
        
    - Event notifications
        

---

### Messaging & Eventing

- **[[Amazon SQS]]**
    
    - Standard vs FIFO queues
        
    - Visibility timeout
        
    - Dead-letter queues
        
- **[[Amazon SNS]]**
    
    - Topics and subscriptions
        
    - Fan-out pattern
        
- **[[Amazon EventBridge]]**
    
    - Event rules
        
    - Event-driven architectures
        

---

## 2. Security (≈26% — VERY IMPORTANT)

### Identity & Access

- **[[AWS Identity and Access Management]]**
    
    - IAM users vs roles vs policies
        
    - Identity-based vs resource-based policies
        
    - Least privilege
        
    - IAM role for Lambda / EC2
        
- **Amazon Cognito**
    
    - User pools vs identity pools
        
    - Authentication vs authorization use cases
        

---

### Secrets & Encryption

- **AWS Secrets Manager**
    
    - Rotation
        
    - Lambda integration
        
- **AWS Systems Manager Parameter Store**
    
    - SecureString vs String
        
    - When to use vs Secrets Manager
        
- **AWS Key Management Service**
    
    - Customer-managed vs AWS-managed keys
        
    - Encryption at rest vs in transit
        

---

## 3. Deployment (≈24%)

### CI/CD

- **AWS CodeCommit**
    
- **AWS CodeBuild**
    
- **AWS CodeDeploy**
    
- **AWS CodePipeline**
    

Key concepts:

- Blue/Green deployments
    
- Canary deployments
    
- Rollbacks
    
- Artifact storage (S3)
    

---

### Infrastructure as Code

- **AWS CloudFormation**
    
    - Templates
        
    - Parameters
        
    - Mappings
        
    - Outputs
        
    - Change sets
        
- **AWS Serverless Application Model**
    
    - Transform section
        
    - SAM CLI
        
    - Local testing
        

---

## 4. Troubleshooting & Optimization (≈18%)

### Monitoring & Logging

- **Amazon CloudWatch**
    
    - Metrics vs logs
        
    - Custom metrics
        
    - Alarms
        
    - Log retention
        
- **AWS X-Ray**
    
    - Traces
        
    - Service maps
        
    - Debugging latency
        

---

### Performance & Cost

- Lambda cold starts
    
- DynamoDB throttling
    
- API Gateway throttling
    
- Retry strategies & exponential backoff
    
- Caching (API Gateway, DynamoDB DAX, ElastiCache)
    

---

## 5. Containers & Microservices (Medium Weight)

- **Amazon Elastic Container Service**
    
- **Amazon Elastic Kubernetes Service**
    
- **AWS Fargate**
    
- **Amazon Elastic Container Registry**
    

Focus on:

- When containers vs Lambda
    
- IAM roles for tasks
    
- Load balancing basics (ALB)
    

---

## 6. Architecture & Design Patterns (Exam Scenarios)

You must recognize:

- Serverless architectures
    
- Event-driven architectures
    
- Fan-out pattern (SNS → SQS)
    
- CQRS basics
    
- Idempotency
    
- Retry + DLQ patterns
    

---