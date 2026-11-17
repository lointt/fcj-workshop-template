---
title: "Week 7 Worklog"
date: 2026-10-26
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Learn Infrastructure as Code with Terraform.
* Set up CI/CD for the frontend with GitHub Actions.
* Get to know Kiro Crew and try it on the project.
* Learn the basics of ETL with AWS Glue and querying data with Athena.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn what Terraform is (Infrastructure as Code) and the basic flow: init, plan, apply, destroy<br>- Install Terraform, configure AWS provider and credentials<br>- Write .tf files to create the VPC, subnets, and S3 bucket<br>- Run plan/apply to check the result on the console, then destroy to save cost | 26/10/2026 | 26/10/2026 | <https://developer.hashicorp.com/terraform/tutorials/aws-get-started> |
| 3 | - Learn how GitHub Actions works: workflow, job, step, secrets<br>- Write `.github/workflows/frontend.yml`: trigger on push to main, install and build the React app, upload build to S3, invalidate the CloudFront cache<br>- Store AWS keys in GitHub Secrets (later try OIDC role)<br>- Push code to test the pipeline and fix errors from the logs | 27/10/2026 | 27/10/2026 | <https://docs.github.com/en/actions> |
| 4 | - Learn what Kiro Crew is: an always-on agent workspace built on Kiro, with persistent memory, schedules, and multiple sub-agents<br>- Install it, read the `.kiro` config (steering, skills)<br>- Give it a small task on the project and check how it works and what it remembers | 28/10/2026 | 28/10/2026 | <https://kiro.dev/docs/crew/> |
| 5 | - Learn AWS Glue and ETL (extract, transform, load): Data Catalog, Crawler, Job<br>- Upload sample CSV data to S3<br>- Create a Crawler to build the table in the Data Catalog<br>- Create a Glue Job to clean/transform the data and write it back to S3 as Parquet | 29/10/2026 | 29/10/2026 | <https://docs.aws.amazon.com/glue/latest/dg/> |
| 6 | - Learn Amazon Athena: serverless SQL on data in S3, uses the Glue Data Catalog<br>- Set the query result location in S3<br>- Run SELECT, WHERE, GROUP BY queries on the table from Glue<br>- Compare CSV vs Parquet in data scanned and cost | 30/10/2026 | 30/10/2026 | <https://docs.aws.amazon.com/athena/latest/ug/> |


### Week 7 Achievements:

* Wrote Terraform files to create the VPC, subnets, and S3 bucket, and ran init/plan/apply/destroy.
* Wrote frontend.yml so every push to main builds the React app and deploys it to S3 + CloudFront automatically.
* Tried Kiro Crew and learned how its memory, schedules, and sub-agents work.
* Built a small ETL flow: CSV on S3, Glue Crawler, Glue Job to Parquet.
* Queried the data with Athena and saw that Parquet scans much less data than CSV.
