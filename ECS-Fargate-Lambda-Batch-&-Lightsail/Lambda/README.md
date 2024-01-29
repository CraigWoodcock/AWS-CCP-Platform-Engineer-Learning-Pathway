# Lambda

- [Lambda](#lambda)
  - [Why use Lambda?](#why-use-lambda)
  - [Benefits](#benefits)
  - [Lambda Container Image](#lambda-container-image)
  - [Lambda Use Cases](#lambda-use-cases)
  - [Creating a Lambda Function](#creating-a-lambda-function)
  - [Creating a Test Event to Test the Function](#creating-a-test-event-to-test-the-function)


## Why use Lambda?

 - No servers, just virtual functions
 - Limited by time - short executions
 - Run on-demand - only runs when needed
 - Scaling is Automated

## Benefits
 - Pay per request compute time
 - Free Tier of 1,000,000 AWS Lambda requests and 400,000 GBs of compute time.
 - Integrated with all AWS Services
 - Event-Driven - Only invokes functions when needed
 - Integrated with many programming languages
 - Easy monitoring through AWS CloudWatch
 - Easy to get more resources per functions(up to 10GB or RAM).
 - Increasing RAM increases CPU and Network quality

## Lambda Container Image

  - The container image must implement the Lambda Runtime API
  - ECS/Fargate is preferred for running arbitrary Docker Images
  
## Lambda Use Cases

  - Diagram shows an image being uploaded to S3 storage
  - AWS Lambda Creates a thumbnail of the image
  - AWS Lambda Pushes new smaller thumbnail back to S3 bucket
  - AWS Lambda pushes Metadata about the image to DynamoDB for caching

![Lambda Serverless Example](<../Screenshots/Screenshot 2024-01-29 121715.png>)

## Creating a Lambda Function

  - Sign into AWS and Search for 'Lambda'
  - Select 'Create a function'
  - We will 'Use a blueprint'
  - Select a blueprint to use (i used 'Hello World' - python)
  - Choose a name
  - Select 'Create a new role with basic Lambda permissions'
  - Create Function


## Creating a Test Event to Test the Function
  - Once the function is created
    - Select 'Test' to create a new test
  - Give the event a name and press 'Save'
  - Now press test again to run the test.      
