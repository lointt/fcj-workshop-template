---
title: "Week 9 Worklog"
date: 2026-11-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Control the input/output safety of LLM applications with Amazon Bedrock Guardrails.
* Understand how to bring AI/ML processing to edge devices with AWS IoT Greengrass.
* Learn the ways to run web apps on Lambda: Function URLs and Web Adapter.
* Understand load balancing with ALB and running containers with Amazon ECS (Fargate/EC2).

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - **Amazon Bedrock Guardrails**: safeguard layer that controls both input (prompt) and output (response) for LLM/Agent applications<br>&emsp;+ 6 controls: Content Filters (hate speech, violence, blocks Prompt Injection/Jailbreak), Denied Topics (ban sensitive topics), Word Filters (profanity, competitor names), Sensitive Information Filters (block or mask PII/Custom Regex such as [EMAIL], [PHONE]), Contextual Grounding Checks (reduce RAG hallucination based on grounding in the source), Automated Reasoning Checks<br>&emsp;+ Usage: integrates with Bedrock Models, Knowledge Bases, and Bedrock Agents, or can be called standalone through the ApplyGuardrail API to protect models outside Bedrock too | 9/11/2026 | 9/11/2026 | <https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html> |
| 3 | - **AWS IoT Greengrass**: cloud service and open-source Edge Runtime that brings AWS processing to edge devices<br>&emsp;+ Capabilities: low-latency local data processing, offline operation when the network is lost, AI/ML inference at the edge, and remote (OTA) software/model updates for many devices<br>&emsp;+ Architecture: package the app as Greengrass Components (Lambda functions, Docker containers, Python scripts) -> deploy from the Cloud to devices running Greengrass Core -> filter data locally and send only important data/alerts to AWS IoT Core or S3 through Stream Manager | 10/11/2026 | 10/11/2026 | <https://docs.aws.amazon.com/greengrass/> |
| 4 | - **AWS Lambda Web Functions** (Lambda Function URLs & Lambda Web Adapter): run web apps and HTTP APIs directly on Lambda<br>&emsp;+ Lambda Function URLs: a dedicated HTTPS endpoint (https://<url-id>.lambda-url.<region>.on.aws) for a Lambda function without paying for API Gateway; supports CORS, streaming responses, and 2 auth modes: AWS_IAM or NONE (public)<br>&emsp;+ Lambda Web Adapter (Lambda Layer / Container extension): runs traditional web frameworks (Next.js, Express.js, FastAPI, Flask, Spring Boot) on Lambda as they are, without rewriting code to the Lambda event handler format | 11/11/2026 | 11/11/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/urls-configuration.html> |
| 5 | - **Amazon ALB (Application Load Balancer)**: Layer 7 load balancer (HTTP/HTTPS, gRPC, WebSockets) in Elastic Load Balancing<br>&emsp;+ Components: Listeners (ports/protocols such as 80, 443), Rules (path-based /api/*, host-based, HTTP headers, query strings), Target Groups (EC2 instances, ECS tasks/IPs, Lambda) with automatic Health Checks<br>&emsp;+ Integration & security: free SSL/TLS certificates via AWS Certificate Manager (SSL offloading), AWS WAF integration against web attacks, Sticky Sessions and authentication via Cognito or OIDC | 12/11/2026 | 12/11/2026 | <https://docs.aws.amazon.com/elasticloadbalancing/latest/application/> |
| 6 | - **Amazon ECS (Elastic Container Service)**: AWS container orchestration service<br>&emsp;+ Components: Cluster (infrastructure group), Task Definition (JSON blueprint declaring the Docker image, CPU/RAM, ports, IAM Task Role, CloudWatch logs), Task (an instance running from a Task Definition), Service (keeps the desired number of Tasks, self-heals on failure, attaches to an ALB)<br>&emsp;+ 2 Launch Types: AWS Fargate (serverless, no server management, billed by the vCPU and memory each Task actually uses) and Amazon EC2 (manage the EC2 cluster yourself to optimize cost for steady workloads or use GPUs) | 13/11/2026 | 13/11/2026 | <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/> |


### Week 9 Achievements:

* Understood the 6 controls of Bedrock Guardrails and how to use them through the ApplyGuardrail API.
* Understood the Greengrass architecture: Components, Core device, Stream Manager, OTA, and offline operation.
* Told apart Lambda Function URLs from API Gateway and knew when to use Lambda Web Adapter.
* Understood ALB Listeners, Rules, Target Groups, and Health Checks, plus ACM and WAF integration.
* Understood ECS Clusters, Task Definitions, Tasks, and Services, and the difference between Fargate and EC2 launch types.
