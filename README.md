# Serverless API using AI

A serverless REST API built on AWS that gives users access to use a AI system to answer questions. Services used to create this are API Gateway, Lambda, DynamoDB, Bedrock(Nova Micro), and CloudWatch Alarms to monitor and alert me of any errors

## Services used 
- **API Gateway** - First to receive the request from the internet
- **Lambda** - Moves the request to where it needs to go by using the code I put in
- **DynamoDB** - Stores the questions and anwsers so that when information needs to be accessed I know where to look
- **Amazon Bedrock(Nova Micro)** - The AI model I used to answer the questions
- **IAM** - Lambda needed permission to DynamoDB and Bedrock to send and access information
- **CloudWatch** - Monitors for errors and send me a alert if a error happens

## How it works
  User sends request > API Gateway > Lambda > Bedrock > DynamoDB > Responds to User

## What I learned 
- Building this project taught me how to troubleshoot real errors.  I ran into two errors. One error was that the Lambda function could not find the DynamoDB to find and store information that the user requested. I used CloudWatch Logs to find the error and the error was in the code. In the code in Lambda I put the wrong name of the table that stores all the information from the user. The name I put for the DynamoDB was serverless-api and Lambda was looking for serverless-api-table. So since I was already in the code I simply removed the "table" out of the serverless-api-table and reran the test via terminal and it worked.The second error was related to the Bedrock model format. Lambda was sending the request in the wrong format for Nova Micro so I had to update the code to match the correct format. I also learned that we use API services everyday and that how everything is linked together to work.
