 Support Ticket System AWS Serverless

## Live URLs
- Frontend (CloudFront): https://d2u7w9mwwy7ay9.cloudfront.net
- API: https://8q6lbz30y9.execute-api.ap-south-1.amazonaws.com/prod/tickets

## Architecture
User -> CloudFront -> S3 (Frontend) -> API Gateway -> Lambda (createTicket) -> SQS -> Lambda (processTicket) -> DynamoDB + SNS
EventBridge Scheduler (Daily 9 AM) -> Lambda (processTicket)

## Services Used
VPC, EC2 (Jenkins), S3, DynamoDB, Lambda, API Gateway, SQS, SNS, EventBridge, CloudWatch, CloudTrail, Budgets, CloudFront, Jenkins

## Jenkins
- Freestyle Job: deploy-frontend-to-s3 - SUCCESS
- Pipeline Job: ticket-pipeline - SUCCESS
- Jenkins URL: http://65.2.172.238:8080

## How to Test
1. Open CloudFront URL
2. Fill form and Submit Ticket
3. Click View All Tickets
4. Check Email for SNS Notification
