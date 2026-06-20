# AI Blog Generation System using AWS Bedrock, Lambda, API Gateway and S3

<img width="1232" height="457" alt="image" src="https://github.com/user-attachments/assets/93dce65f-5c23-4015-bef0-f6fbb0e7403c" />


## Overview

This project is a serverless AI-powered blog generation system built using AWS services. The application accepts a blog topic through an API endpoint, generates a blog using a Large Language Model (LLM) hosted on Amazon Bedrock, and stores the generated content in an Amazon S3 bucket.

The project demonstrates how to integrate Generative AI with AWS serverless architecture for automated content generation.

---

## Features

* Generate AI-powered blogs from user-provided topics
* Serverless architecture using AWS Lambda
* REST API endpoint using API Gateway
* Blog generation using Amazon Bedrock (Meta Llama Model)
* Automatic storage of generated blogs in Amazon S3
* API testing using Postman
* Scalable and cost-effective cloud-native solution

---

## Architecture

User Request (Postman)
|
v
AWS API Gateway
|
v
AWS Lambda Function
|
v
Amazon Bedrock (Meta Llama)
|
v
Generated Blog
|
v
Amazon S3 Bucket

---

## Tech Stack

### Cloud Services

* AWS Lambda
* Amazon Bedrock
* Amazon S3
* Amazon API Gateway
* AWS IAM

### Programming Language

* Python

### Libraries

* boto3
* botocore
* json

### Testing Tool

* Postman

---

## Project Workflow

1. User sends a POST request containing a blog topic.
2. API Gateway receives the request.
3. API Gateway triggers the Lambda function.
4. Lambda extracts the blog topic from the request body.
5. Lambda invokes a Meta Llama model through Amazon Bedrock.
6. Bedrock generates a blog based on the provided topic.
7. Lambda stores the generated blog in an Amazon S3 bucket.
8. API Gateway returns a success response to the user.

---
<img width="1067" height="856" alt="image" src="https://github.com/user-attachments/assets/2c9ff9a3-3c54-4329-a7a7-20be77b39f2d" />

After hitting the endpoint the generated message will be stored in s3 bucket
<img width="1757" height="537" alt="image" src="https://github.com/user-attachments/assets/47ed5730-805a-42d5-a4e1-cd502a1f7f09" />

---> Note: I also provided my output in blog-output folder in txt formet. You can refer and see how does the output looks.

## API Endpoint

### POST Request

```http
POST /blog-generation
```

### Request Body

```json
{
    "blog_topic": "Artificial Intelligence"
}
```

### Success Response

```json
{
    "message": "Blog generated successfully"
}
```

---

## AWS Services Used

### Amazon Bedrock

Used for Generative AI blog creation using Meta Llama models.

### AWS Lambda

Executes the serverless Python function and handles the complete workflow.

### Amazon S3

Stores generated blog files in text format.

### API Gateway

Exposes a REST API endpoint for users.

### IAM

Provides secure permissions between AWS services.

---

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Required IAM Permissions

### Bedrock Access

```json
{
  "Effect": "Allow",
  "Action": [
    "bedrock:InvokeModel"
  ],
  "Resource": "*"
}
```

### S3 Access

```json
{
  "Effect": "Allow",
  "Action": [
    "s3:PutObject"
  ],
  "Resource": "*"
}
```

## Learning Outcomes

Through this project, I learned:

* Serverless application development
* AWS Lambda deployment
* API Gateway integration
* Amazon Bedrock and Generative AI
* Amazon S3 object storage
* IAM roles and permissions
* API testing using Postman
* Cloud-native application architecture

---

