---
title: "Week 4 Worklog"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Build the foundation of a serverless e-commerce website on AWS (motorcycle parts store).
* Implement user authentication with Amazon Cognito (JWT) and host a React frontend on S3 + CloudFront.
* Design the serverless backend: DynamoDB, Lambda, and API Gateway.
* Build an asynchronous order-processing flow with SNS, SQS, and EventBridge.
* Connect the frontend to the backend to retrieve real data from DynamoDB.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Amazon Cognito: Manage registration, login, and JWT token issuance for users and admins.<br>- Create User Pool: <br>&emsp;+ options for sign-in identifier: Email<br>&emsp;+ select attributes: name and phone_number<br>&emsp;+ URL: fill Cloudfront Distribution URL<br>- Retrieve Configuration Information for the Frontend:<br>&emsp;+ User Pool ID<br>&emsp;+ App Client ID | 5/10/2026   | 5/10/2026      | <https://awsstudygroup.com/> |
| 3   | - Create a React interface and upload it to S3; connect to Cognito; deploy on CloudFront:<br>&emsp;+ Initialize a React project: npx create-react-app phutungxemay<br>&emsp;+ Install the AWS Amplify library to connect to Cognito: npm install aws-amplify @aws-amplify/ui-react<br>&emsp;+ Add AWS Cognito connection configuration file: src/aws-exports.js<br>&emsp;+ Create a simple E-commerce + Auth interface: src/App.js<br>&emsp;+ Package the project into static files and upload it to S3: npm run build<br>&emsp;+ Check on domain CloudFront: https://xxxxxxxxx.cloudfront.net | 6/10/2026   | 6/10/2026      | <https://awsstudygroup.com/> |
| 4   | - Create DynamoDB: CatalogDB and OrdersDB<br>- Create IAM Role for Lambda Functions<br>- Initialize Lambda functions:<br>&emsp;+ Read/WriteCatalogLambda to read/write products in DynamoDB<br>&emsp;+ Cart/OrderLambda to add products to the cart and save order information<br>&emsp;+ PaymentWebhookLambda to receive webhooks from MoMo/VNPay payment gateways.<br>&emsp;+ InventoryShippingWorkerLambda to manage inventory and connect third-party shipping API<br>&emsp;+ Add trigger to connect SQS in InventoryShippingWorkerLambda   | 7/10/2026      | 7/10/2026      | <https://awsstudygroup.com> |
| 5   | - Create Amazon SNS Topic (Email Notification)<br>- Create Amazon SQS Queue (Order Processing)<br>- Configuring Amazon EventBridge (Event Bus)<br>&emsp;+ Create Subscriber for SQS <br>&emsp;+ Create Subscriber for SNS                           | 8/10/2026 | 8/10/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Initialize Amazon API Gateway (REST API):<br>&emsp;+ Create an Authorizer with Cognito (JWT Security)<br>&emsp;+ Create Resource:  /products, /orders,  /webhook/payment<br>&emsp;+ Create Method: GET, POST, POST<br>&emsp;+ Enable CORS at /products: Access-Control-Allow-Methods: Tick GET, OPTIONS<br>&emsp;+ Press Deploy API<br>- Connect Frontend and Backend to get actual data from DynamoDB (CatalogDB) via API Gateway and Lambda                                                                                     | 9/10/2026 | 9/10/2026      | <https://cloudjourney.awsstudygroup.com/> |


### Week 4 Achievements:

* Created an Amazon Cognito User Pool (Email sign-in, name and phone_number attributes) and obtained the User Pool ID and App Client ID for the frontend configuration.
* Built a React (E-commerce + Auth) interface with AWS Amplify, packaged it into static files, uploaded it to S3, and distributed it through CloudFront.
* Created the DynamoDB tables (CatalogDB, OrdersDB), the IAM Role, and the Lambda functions for catalog, cart/order, payment webhook (MoMo/VNPay), inventory, and shipping handling.
* Configured an SNS Topic (email notification), an SQS Queue (order processing), and an EventBridge Event Bus with their subscribers, and connected the SQS trigger to the Lambda function.
* Initialized API Gateway (REST API) with a Cognito Authorizer, the /products, /orders, and /webhook/payment resources, enabled CORS, and deployed the API.
* Successfully connected the frontend to the backend, displaying real product data from DynamoDB through API Gateway and Lambda.
