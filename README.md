# Cloud Fun Facts Generator (AWS Serverless Project)

## Project Overview

The Cloud Fun Facts Generator is a serverless application that returns
random facts about cloud computing.

Users click a button on a web page and receive a fun fact about the cloud.
Behind the scenes, an API triggers a Lambda function that retrieves a fact
from DynamoDB and returns it to the frontend.

This project demonstrates how multiple AWS services work together
to create a simple serverless application.

---

## Architecture

User
 ↓
Frontend Website
 ↓
API Gateway
 ↓
Lambda Function
 ↓
DynamoDB
 ↓
Response returned to user

---

## AWS Services Used

- AWS Lambda
- Amazon API Gateway
- Amazon DynamoDB
- AWS IAM
- AWS Amplify (for hosting frontend)
- Amazon CloudWatch (logs)

---

## Features

- Serverless backend
- API-based architecture
- Database-driven responses
- Simple web frontend
- Cloud logging and monitoring

---

## Architecture Diagram

![Architecture Diagram](architecture/architecture-diagram.png)

---

## Screenshots

### Application Interface
![App](screenshots/app-interface.png)

### API Gateway Endpoint
![API](screenshots/api-gateway.png)

### Lambda Function
![Lambda](screenshots/lambda-function.png)

### DynamoDB Table
![DynamoDB](screenshots/dynamodb-table.png)

---

## Example Lambda Function

```python
import json

def lambda_handler(event, context):
    # TODO implement
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }
import random
import json

def lambda_handler(event, context):
    facts = [
        "AWS S3 was launched in 2006 and still rules cloud storage.",
        "Cloud computing can save companies up to 30% on IT costs.",
        "EC2 was one of the first AWS services to change IT forever.",
       
