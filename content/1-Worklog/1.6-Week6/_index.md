---
title: "Week 6 Worklog"
date: 2026-10-19
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Understand the concepts of Amazon Bedrock, Bedrock AgentCore, SageMaker AI, AWS Continuum, and AWS RAM.
* Request and obtain access to AI models in Bedrock for the Free Tier account, and call them from the console and SDK.
* Build and deploy a simple AI agent with Bedrock AgentCore.
* Practice the basic ML workflow on SageMaker AI: notebook, training, and model deployment.
* Learn AI-driven code security with Continuum and resource sharing across accounts with RAM.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Amazon Bedrock concepts: managed service to access foundation models (FMs) through a single API; Model catalog, Playground, `InvokeModel` and `Converse` APIs<br>- Request access to AI models for the Free Tier account:<br>&emsp;+ Open a model in the Bedrock playground / Model catalog to start model access<br>&emsp;+ For Anthropic models, submit the one-time use case form and wait until the status changes from PENDING to AVAILABLE<br>&emsp;+ Grant the IAM identity the AWS Marketplace permissions needed for the first use of third-party models<br>- Hands-on: chat with the approved model in the Playground and call it with `boto3` (`bedrock-runtime`, `converse`) | 19/10/2026 | 19/10/2026 | <https://docs.aws.amazon.com/bedrock/latest/userguide/model-access.html> |
| 3 | - Amazon Bedrock AgentCore concepts: platform to build, deploy, and operate AI agents securely at scale; main components: Runtime, Memory, Gateway, Identity, Observability, Code Interpreter, Browser<br>- Hands-on:<br>&emsp;+ Create an IAM role/permissions for AgentCore<br>&emsp;+ Write a simple agent and deploy it to AgentCore Runtime<br>&emsp;+ Invoke the agent and review logs/traces in CloudWatch<br>&emsp;+ Try AgentCore Memory to keep conversation context<br>&emsp;+ Delete the resources after practice to avoid costs | 20/10/2026 | 20/10/2026 | <https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/> |
| 4 | - Amazon SageMaker AI concepts: managed ML platform for building, training, and deploying models; Studio, notebooks, training jobs, endpoints, JumpStart<br>- Hands-on:<br>&emsp;+ Create a SageMaker domain and open Studio (with an execution role and S3 bucket)<br>&emsp;+ Run a notebook: load a sample dataset, train a simple model, and review the results<br>&emsp;+ Try SageMaker JumpStart: deploy a pre-trained model to a real-time endpoint and test inference<br>&emsp;+ Delete endpoints, apps, and the domain after practice to avoid costs | 21/10/2026 | 21/10/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/> |
| 5 | - AWS Continuum concepts: AI-driven security platform (launched June 2026) that finds, validates, and recommends fixes for software vulnerabilities; four phases: ingest/scan, prioritize, validate in a sandbox, recommend fixes; learn mode (human in the loop) and enforce mode (automated remediation); includes Continuum code scanning, pen testing, and threat modeling (preview)<br>- Hands-on: Continuum code vulnerability capability is in gated preview, so request access and study the workflow, the learn-mode approach, and how it fits with IAM and CloudWatch security practices | 22/10/2026 | 22/10/2026 | <https://aws.amazon.com/continuum/> |
| 6 | - AWS Resource Access Manager (RAM) concepts: share AWS resources with other accounts, an organization, or OUs without duplicating them; resource shares, principals, managed permissions<br>- Hands-on:<br>&emsp;+ Create a resource share (for example, a VPC subnet)<br>&emsp;+ Add principals (another AWS account or an AWS Organization) and select managed permissions<br>&emsp;+ Accept the invitation in the receiving account and verify the shared resource is visible<br>&emsp;+ Delete the resource share after practice | 23/10/2026 | 23/10/2026 | <https://docs.aws.amazon.com/ram/latest/userguide/> |


### Week 6 Achievements:

* Understood Amazon Bedrock and submitted the access requests for AI models on the Free Tier account (including the Anthropic use case form), then used the models in the Playground and through `boto3`.
* Understood the Bedrock AgentCore components and deployed a simple agent to AgentCore Runtime, with logs/traces and memory.
* Understood SageMaker AI and practiced creating a domain, running a notebook, training a simple model, and deploying a JumpStart model to an endpoint, then cleaned up the resources.
* Understood the AWS Continuum workflow (scan, prioritize, validate, fix) and its learn/enforce modes, and requested access to the gated preview.
* Understood AWS RAM and shared a resource (VPC subnet) with another account, then verified it from the receiving account.
* Learned to clean up resources after each lab to control costs on the Free Tier.
