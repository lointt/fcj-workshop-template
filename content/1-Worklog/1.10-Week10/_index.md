---
title: "Week 10 Worklog"
date: 2026-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Explore managed AWS AI services for vision and text: Amazon Rekognition, Amazon Textract, and Amazon Comprehend.
* Combine Amazon Rekognition with Amazon Athena to query image analysis results using SQL.
* Understand secrets management and encryption on AWS with AWS Secrets Manager and AWS KMS.
* Learn serverless workflow orchestration with AWS Step Functions.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - **Amazon Rekognition**: deep learning–based image and video analysis service<br>&emsp;+ Tested `DetectLabels` via AWS CLI on 30 images from the Imagenette dataset stored in S3<br>&emsp;+ Compared `MinConfidence` thresholds (80 vs. 55) to observe the trade-off between precision and recall<br>&emsp;+ Exported JSON results to S3 and queried label statistics with Amazon Athena | 16/11/2026 | 16/11/2026 | <https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html> |
| 3 | - **Amazon Textract**: automated text, form, and table extraction from scanned documents and PDFs<br>&emsp;+ Learned the difference between synchronous APIs (`DetectDocumentText`, `AnalyzeDocument`) and asynchronous APIs for multi-page PDFs<br>&emsp;+ Explored use cases such as invoice processing and digitizing product catalogs | 17/11/2026 | 17/11/2026 | <https://docs.aws.amazon.com/textract/latest/dg/what-is.html> |
| 4 | - **Amazon Comprehend**: Natural Language Processing (NLP) service for extracting insights from text<br>&emsp;+ Learned key features: Sentiment Analysis, Entity Recognition, Key Phrase Extraction, and PII detection<br>&emsp;+ Explored how Comprehend can classify customer feedback and support tickets | 18/11/2026 | 18/11/2026 | <https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html> |
| 5 | - **AWS Secrets Manager & AWS KMS**: managing credentials and encryption keys<br>&emsp;+ Stored API keys and credentials (Gemini API, VNPay, GHN, Gmail SMTP) in Secrets Manager instead of hardcoding in Lambda environment variables<br>&emsp;+ Understood symmetric KMS keys, envelope encryption, and key policies | 19/11/2026 | 19/11/2026 | <https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html> |
| 6 | - **AWS Step Functions**: visual workflow orchestration for distributed serverless applications<br>&emsp;+ Learned Amazon States Language (ASL), Task/Choice/Parallel states, error handling (`Retry`, `Catch`)<br>&emsp;+ Compared Standard Workflows (long-running, exactly-once) vs. Express Workflows (high-volume, short duration) | 20/11/2026 | 20/11/2026 | <https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html> |

### Week 10 Achievements:

* Ran an end-to-end image analysis pipeline using Amazon Rekognition `DetectLabels`, S3, and Amazon Athena SQL queries.
* Understood how Amazon Textract extracts structured data (forms, tables) from documents and how Amazon Comprehend analyzes text sentiment and entities.
* Applied AWS Secrets Manager and KMS to secure third-party API keys and sensitive configuration.
* Understood AWS Step Functions state machines, retry/catch error handling, and when to choose Standard vs. Express workflows.
