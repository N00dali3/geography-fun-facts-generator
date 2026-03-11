# Geography Fun Facts Generator (AWS Serverless Project) 
<img width="100" height="100" alt="icons8-geography-100" src="https://github.com/user-attachments/assets/62c3f7d5-3940-44ed-a03f-04a4000b545d" />

## Project Overview

The Geography Fun Facts Generator is a serverless application that returns
random geography facts.

Users click a button on a web page and receive a fun geography fact.
Behind the scenes, an API triggers a Lambda function that retrieves a fact
from DynamoDB and returns it to the frontend.

This project demonstrates how multiple AWS services work together
to create a simple serverless application.


## Architecture

User
→
Frontend Website
 →
API Gateway
→
Lambda Function
→
DynamoDB
→
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
import random
import json

def lambda_handler(event, context):
    facts = [
        "The world's largest desert is actually Antarctica, covering 5.5 million square miles, not the Sahara.",
        "Volcano Island in the Philippines holds a lake, which has an island in it, which has a smaller lake, which contains an even smaller island called Vulcan Point.",
        "Russia has more surface area than Pluto.",
    ]
    
    fact = random.choice(facts)
    return {
        "statusCode": 200,
        "headers": {"Content-Type": "application/json"},
        "body": json.dumps({"fact": fact})
    }
