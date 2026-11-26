---
title: "Blogs Posted"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

This section lists and introduces the technical blogs I have posted to [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj) during my internship.

### [Blog 1 - Amazon Bedrock AgentCore: The Missing Infrastructure for Production AI Agents](3.1-blog1/)
Introduces **Amazon Bedrock AgentCore**, a modular, framework-agnostic AWS platform for deploying and operating AI agents at production scale. Covers its core building blocks (Runtime, Memory, Gateway, Identity, Code Interpreter/Browser, Observability, Evaluations, and Policy with Cedar) along with a hands-on quickstart using the AgentCore CLI.

### [Blog 2 - AWS IAM Access Analyzer: Enforcing Least Privilege the Right Way](3.2-blog2/)
Explains how **AWS IAM Access Analyzer** uses Automated Reasoning to detect externally shared resources and enforce the Least Privilege principle. Walks through a 5-step workflow from Dev to Production using CloudTrail Data Events, Policy Generation, Policy Validation, External Access Analyzer, and Unused Access Analyzer, complete with a before/after JSON policy example.

### [Blog 3 - Amazon Rekognition with Amazon Athena: Analyzing Images with AI and Querying Results with SQL](3.3-blog3/)
Demonstrates how to combine **Amazon Rekognition** (`DetectLabels`) and **Amazon Athena** to automatically label images stored in S3 and run SQL analytics on the results. Includes a hands-on experiment on 30 Imagenette images comparing `MinConfidence` thresholds (80 vs. 55), cost breakdown, and IAM/privacy best practices.
