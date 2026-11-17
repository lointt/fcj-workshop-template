---
title: "Week 8 Worklog"
date: 2026-11-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Learn to evaluate the quality of RAG applications with Amazon Bedrock Evaluation.
* Understand how to monitor and audit AWS account activity with CloudTrail and GuardDuty.
* Explore Amazon Q Business for building an internal AI assistant for enterprises.
* Apply the Least Privilege principle with IAM Access Analyzer.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - **Amazon Bedrock Evaluation**: evaluate the quality of RAG applications<br>&emsp;+ 2 evaluation modes: "Retrieve only" and "Retrieve and Generate"<br>&emsp;+ "Retrieve only" metrics: context relevance, context coverage<br>&emsp;+ "Retrieve and Generate" metrics: correctness, completeness, helpfulness, logical coherence...<br>&emsp;+ Process: prepare a question/answer set (JSONL) -> upload to S3 -> in the Bedrock console choose the RAG source, evaluation mode, judge model, metrics, and response-generating model -> review the result report | 2/11/2026 | 2/11/2026 | <https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation.html> |
| 3 | - **AWS CloudTrail**:<br>&emsp;+ Records changes made through the AWS Management Console, AWS CLI, AWS SDKs & APIs, and AWS internal automation<br>&emsp;+ Event types: Management Events, Data Events, Insights Events (JSON)<br>&emsp;+ Storage: "Event History" keeps Management Events for only 90 days; use "Trails" to deliver compressed .json.gz files to an Amazon S3 bucket for longer retention | 3/11/2026 | 3/11/2026 | <https://docs.aws.amazon.com/awscloudtrail/latest/userguide/> |
| 4 | - **AWS GuardDuty**: intelligent threat detection using Machine Learning<br>&emsp;+ Input data: CloudTrail Events, VPC Flow Logs, DNS Query Logs<br>&emsp;+ Finding severity: Low, Medium, High<br>&emsp;+ Standard format: ThreatPurpose:ResourceType/ThreatFamilyName.DetectionMechanism<br>&emsp;+ Common findings: CryptoCurrency:EC2/BitcoinTool.B!DNS; UnauthorizedAccess:IAMUser/InstanceCredentialExfiltration.OutsideAWS | 4/11/2026 | 4/11/2026 | <https://docs.aws.amazon.com/guardduty/latest/ug/> |
| 5 | - **Amazon Q Business**: generative AI assistant for enterprises based on internal data (Enterprise RAG)<br>&emsp;+ Core components: Data Sources (40+ connectors: S3, SharePoint, Jira, Confluence, Slack...), Index (semantic indexing), Retriever, and Plugins (perform actions in third-party systems)<br>&emsp;+ Security & permissions: integrates with AWS IAM Identity Center and uses document-level ACLs, so users only get answers from documents they are allowed to view<br>&emsp;+ Process: create an Application -> connect IAM Identity Center -> add a Data Source & Sync it into the Index -> configure Guardrails/Admin Controls -> deploy the Web Experience for end users | 5/11/2026 | 5/11/2026 | <https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/> |
| 6 | - **IAM Access Analyzer**: analyzes policies with Automated Reasoning and refines permissions toward Least Privilege<br>&emsp;+ 4 features: External Access Analysis (finds resources shared outside the Zone of Trust, free), Unused Access Analysis (scans forgotten roles/users/access keys, paid), Policy Validation (checks syntax and 100+ security rules), Policy Generation (generates a JSON policy from real activity history)<br>&emsp;+ Least Privilege process: enable a CloudTrail Trail (Management + Data Events) and run tests in Dev -> use Generate policy on the IAM Role to scan CloudTrail logs -> restrict Resource ARNs and check with Policy Validation -> attach the final policy to Production and enable External Access Analyzer for monitoring | 6/11/2026 | 6/11/2026 | <https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html> |


### Week 8 Achievements:

* Understood the Bedrock Evaluation flow for RAG: the 2 modes, the metrics, and how to read the report.
* Understood which events CloudTrail records and how to keep logs beyond 90 days with Trails + S3.
* Understood how GuardDuty analyzes logs to detect threats, and how to read finding severity and names.
* Understood the Amazon Q Business architecture: Data Sources, Index, Retriever, Plugins, and access control with IAM Identity Center + ACLs.
* Understood the 4 features of IAM Access Analyzer and the process of generating Least Privilege policies from CloudTrail logs.
