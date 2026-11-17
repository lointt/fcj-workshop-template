---
title: "Week 5 Worklog"
date: 2026-10-12
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Build the private network foundation on AWS: VPC, subnets, gateways, route tables, and VPC endpoints.
* Deploy Amazon OpenSearch inside a private subnet to serve as the search/vector store for the chatbot.
* Keep OpenSearch in sync with DynamoDB in real time using DynamoDB Streams.
* Build an AI chatbot backend with Lambda that retrieves data from OpenSearch and calls the Gemini API.
* Enable real-time two-way chat between the frontend and backend with API Gateway (WebSocket API).

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Create VPC<br>- Add 4 subnets: Public AZ1, Public AZ2, Private AZ1, Private AZ2<br>- Create Internet Gateway<br>- Create NAT Gateway so Private Subnets can reach the internet<br>- Configure Public Route Table (route to IGW)<br>- Configure Private Route Table (route to NAT Gateway) | 12/10/2026 | 12/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Create Gateway Endpoint for DynamoDB<br>- Create Security Group for Interface Endpoint: an Interface Endpoint creates an ENI directly within a private subnet, so a security group is used to control traffic flow<br>- Create Interface Endpoint for AWS Secrets Manager | 13/10/2026 | 13/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Create OpenSearch Domain:<br>&emsp;+ Create Security Group for OpenSearch<br>&emsp;+ Create OpenSearch Domain inside a private subnet of the VPC<br>&emsp;+ Select 1-AZ, 1 data node, t3.small.search, EBS volume type: General Purpose (SSD) - gp3, EBS storage size per node: 10 GiB to save cost during the development/testing phase | 14/10/2026 | 14/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Create a Lambda function that runs once to generate the vector index for OpenSearch<br>- Create DynamoDBSyncToOS Lambda: use DynamoDB Streams to capture real-time data changes from DynamoDB and propagate them to OpenSearch<br>- Create ChatOrchestratorHandler Lambda: use OpenSearch for retrieval and call the Gemini API to answer customers | 15/10/2026 | 15/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - Configure Amazon API Gateway (WebSocket API):<br>&emsp;+ $connect: when the frontend opens a WebSocket connection, API Gateway generates a unique `connectionId`<br>&emsp;+ $disconnect: triggered when the frontend closes the tab or loses network connectivity<br>&emsp;+ sendMessage: receives chat messages from the client and triggers `ChatOrchestratorHandler`<br>&emsp;+ Two-way communication: since AI processing in Lambda can take several seconds, instead of waiting for an HTTP response, the Lambda function uses the `boto3.client('apigatewaymanagementapi')` SDK to push the response back to the client's specific `connectionId` | 16/10/2026 | 16/10/2026 | <https://cloudjourney.awsstudygroup.com/> |


### Week 5 Achievements:

* Created a VPC with 2 public and 2 private subnets across 2 AZs, an Internet Gateway, and a NAT Gateway, with public and private route tables configured correctly.
* Created a Gateway Endpoint for DynamoDB and an Interface Endpoint for AWS Secrets Manager, with a Security Group controlling endpoint traffic, so private resources reach AWS services without using the public internet.
* Deployed an Amazon OpenSearch Domain inside a private subnet (1 AZ, 1 t3.small.search node, 10 GiB gp3) with a dedicated Security Group, optimized for development/testing cost.
* Created a one-time Lambda to generate the OpenSearch vector index, and the DynamoDBSyncToOS Lambda that propagates DynamoDB changes to OpenSearch through DynamoDB Streams.
* Created the ChatOrchestratorHandler Lambda that uses OpenSearch for retrieval and the Gemini API to answer customer questions.
* Configured API Gateway (WebSocket API) with $connect, $disconnect, and sendMessage routes, and pushed AI responses back to each client's connectionId for real-time two-way communication.
