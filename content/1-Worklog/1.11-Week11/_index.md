---
title: "Week 11 Worklog"
date: 2026-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Complete end-to-end deployment of the Serverless E-Commerce & Full-Duplex RAG Chatbot workshop.
* Verify all backend microservices, asynchronous EventBridge/SQS workers, and third-party integrations (VNPay, GHN, Gmail SMTP).
* Test the Full-Duplex RAG Chatbot, DynamoDB Streams CDC sync, and Human Handover flow.
* Harden security, verify CloudWatch monitoring/alarms, and practice clean resource teardown.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - **Frontend SSR Deployment & Verification**:<br>&emsp;+ Built and deployed the Next.js 14 SSR frontend to S3 + Lambda SSR behind Amazon CloudFront and Edge WAF<br>&emsp;+ Verified product image delivery from S3, security headers, and Cognito authentication (sign-up, sign-in, forgot password) | 23/11/2026 | 23/11/2026 | <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/> |
| 3 | - **Backend Microservices & Event-Driven Testing**:<br>&emsp;+ Tested all 5 Lambda microservices (`User`, `Catalog`, `Cart`, `Order`, `Payment Webhook`) via REST API Gateway<br>&emsp;+ Verified VNPay Sandbox checkout and EventBridge → SQS → Workers (Inventory deduction, GHN Sandbox shipment creation, Gmail SMTP notification) | 24/11/2026 | 24/11/2026 | <https://docs.aws.amazon.com/eventbridge/latest/userguide/> |
| 4 | - **Full-Duplex RAG Chatbot & CDC Verification**:<br>&emsp;+ Tested WebSocket API authentication (`ChatAuthorizer`) for both guest and Cognito-authenticated sessions<br>&emsp;+ Verified DynamoDB Streams → `DynamoDBSyncToS3` embedding sync, in-chat product recommendations, and `HumanRequested` email escalation | 25/11/2026 | 25/11/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api.html> |
| 5 | - **Security Hardening & Monitoring Setup**:<br>&emsp;+ Reviewed IAM Roles with Least Privilege and checked findings in IAM Access Analyzer<br>&emsp;+ Configured CloudWatch Logs, CloudWatch Alarms for Lambda errors, and SNS email alerts | 26/11/2026 | 26/11/2026 | <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/> |
| 6 | - **Workshop Documentation & Cleanup Practice**:<br>&emsp;+ Completed the step-by-step Workshop guide (sections 5.1–5.5) with screenshots and verification steps<br>&emsp;+ Practiced full cleanup: emptying versioned S3 buckets, running `terraform destroy`, and removing leftover CloudWatch log groups and IAM resources | 27/11/2026 | 27/11/2026 | <https://developer.hashicorp.com/terraform/cli/commands/destroy> |

### Week 11 Achievements:

* Verified the complete Serverless E-Commerce storefront and all 5 backend microservices end-to-end.
* Confirmed asynchronous order fulfillment (Inventory, GHN Shipping, Gmail Notification) works reliably with EventBridge, SQS, and DLQ.
* Verified real-time RAG Chatbot responses, DynamoDB Streams vector sync, and the Human Handover flow.
* Completed the full Workshop documentation and verified clean teardown with `terraform destroy` to avoid ongoing AWS charges.
