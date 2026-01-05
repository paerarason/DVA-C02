
---

## 1. Function Lifecycle & Handlers

The execution environment follows a strict three-phase lifecycle. Understanding this helps you optimize for performance and cost.

- **Init Phase:** Lambda freezes the environment after code is uploaded. It initializes the runtime, downloads your code, and runs the **global code** (code outside the handler).
    
- **Invoke Phase:** The specific handler function is called to process the incoming event.
    
- **Shutdown Phase:** If no more events arrive, the environment is terminated.
    
- **The Handler:** This is the entry point for your code. It typically takes two arguments: `event` (data about the trigger) and `context` (runtime information like remaining time).
    

---

## 2. Resource Scaling (Memory vs. CPU)

In Lambda, you do not configure CPU directly. It is a **proportional relationship**.

- **Scaling:** As you increase **Memory** (from 128 MB to 10 GB), AWS linearly increases the available **CPU power** and network bandwidth.
    
- **Exam Tip:** If a function is CPU-bound (e.g., heavy encryption or image processing), the solution is to increase the Memory setting. At approximately **1,769 MB**, a function has the equivalent of one full vCPU.
    

---

## 3. Timeout & Environment Variables

- **Timeout:** The maximum time a function can run is **15 minutes**. If your task takes longer, you should consider using **AWS Step Functions** or **AWS Fargate**.
    
- **Environment Variables:** These are key-value pairs used to pass configuration (like database connection strings) without changing the code. They can be encrypted using **AWS KMS**.
    

---

## 4. Concurrency (Reserved vs. Provisioned)

Concurrency refers to the number of requests your function is handling at the same time.

|**Feature**|**Reserved Concurrency**|**Provisioned Concurrency**|
|---|---|---|
|**Purpose**|Guarantees capacity for a function and acts as a "cap" (limit).|Keeps environments "warm" to eliminate **cold starts**.|
|**Scaling**|Prevents one function from using the whole account limit.|Pre-initializes the Init phase before a request arrives.|
|**Cost**|No additional charge.|High cost (you pay for the uptime of the "warm" instances).|

---

## 5. Event Sources

Lambda is "event-driven." The way it handles events depends on the source:

- **S3:** Asynchronous. S3 sends an event to Lambda when a file is uploaded.
    
- **SQS:** Poll-based. Lambda polls the queue and processes messages in batches.
    
- **DynamoDB Streams:** Poll-based. Lambda reads from the stream to react to database changes (e.g., sending an email when a new user is added).
    
- **API Gateway:** Synchronous. The user waits for a response from the Lambda function.
    

---

## 6. Lambda Layers

**Layers** allow you to pull common code or libraries (like NumPy or the AWS SDK) out of your main function deployment package.

- **Benefit:** Reduces the size of your deployment ZIP, makes the console editor usable for larger projects, and allows multiple functions to share the same dependencies.
    
- **Limit:** You can use up to **5 layers** per function.
    

---

## 7. VPC-Enabled Lambda (Cold Starts)

When you connect a Lambda to a VPC (to access an RDS database or private EC2), it used to be very slow due to "cold starts."

- **Hyperplane ENIs:** Modern Lambda uses a shared networking service (Hyperplane) that maps a single network interface to multiple execution environments. This has **greatly reduced** cold start times for VPC functions.
    
- **Internet Access:** A Lambda inside a VPC **cannot** access the public internet unless you have a **NAT Gateway** in a public subnet. It does not get a public IP by default.
    

---

**Next Step:** Would you like me to walk through a practice scenario where we choose between SQS and DynamoDB Streams as a Lambda trigger?

AWS Lambda Concurrency Explained

This video is relevant because it clearly distinguishes between Reserved and Provisioned concurrency, which is a common source of confusion on the Associate-level exams.