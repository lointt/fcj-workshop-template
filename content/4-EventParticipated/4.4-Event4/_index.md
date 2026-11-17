---
title: "Event 4"
date: 2026-11-15
weight: 1
chapter: false
pre: " <b> 4.4. </b> "
---

# Summary Report: “FPT University Workshop – From Prototype to Production”

### Event Information

- **Event**: FPT University Workshop, organized by First Cloud AI Journey (FCAJ)
- **Theme**: Secure, reliable and scalable enterprise AI on the cloud
- **Format**: Workshop with two main parts: moving AI from prototype to production, and case studies.

### Event Objectives

- Explain the gap between an academic AI prototype and an enterprise AI system
- Present the four pillars of production AI (security, scalability, reliability and cost) and how the cloud supports them
- Learn from real case studies: Cox Automotive, Mobileye and Duolingo
- Introduce Amazon Bedrock AgentCore as a foundation for running agents in an enterprise

### Speakers

- **Khang Duong** – FCAJ member
- **Phuong Huyen** – AI Engineer Fresher, FPT Software
- **Nguyen Lam Anh** – AI Engineer, FCAJ

### Key Highlights

#### Session 1: From Prototype to Production – Secure, Reliable, Scalable Enterprise AI on the Cloud

**One restaurant, one story**

The speaker used a restaurant analogy throughout the session:

- **Prototype** = a home kitchen
- **Enterprise AI** = a restaurant chain
- **Cloud** = a central kitchen

**AI in the enterprise**

- The flow is Data (ingredients) → AI model (the chef) → Feature (the dish) → Users (customers)
- AI is usually a feature inside a product, for example recommendations, a support chatbot or fraud detection

**Academic AI vs. enterprise AI**

| Aspect | Academic AI (home kitchen) | Enterprise AI (restaurant chain) |
|---|---|---|
| Goal | Accuracy | Business value |
| Data | Clean, fixed dataset | Real, ever-changing data |
| Users | A few people | Millions of users |
| Operation | One-off run | 24/7, no downtime |

**More than a model**

- The model is only “the recipe”. A production system also needs a data pipeline, security, scalability, reliability, monitoring and cost control
- **Elastic scalability**: a fixed kitchen wastes capacity when demand is low and fails when demand peaks, while an elastic kitchen follows demand. On AWS, Lambda automatically clones itself, Auto Scaling adds or removes capacity, and a Load Balancer shares the load
- **Reliability**: if one oven breaks, a backup is ready. Tools include health checks, retry, failover and alarms
- **Cost efficiency**: do not keep everything running when nobody is there. Use pay-per-use, right-sizing and caching

**The role of the cloud**

- Built-in security, scaling on demand, backup zones for reliability and pay-as-you-go pricing
- The shared responsibility is clear: AWS manages the infrastructure, and you manage your data and usage

#### Session 2: From Prototype to Production – Case Study

**Cox Automotive**

- 29,000+ employees on five continents, 2.3 billion online interactions a year (first-party data) and 57 agentic AI opportunities identified
- Business areas: car buying and selling, auctions, dealer software and fleet services
- Key question: “How do you build automated AI solutions that users will trust?”
- Approach: standardize the foundation first with Amazon Bedrock AgentCore
  - **AgentCore Runtime**: one runtime for all agents, covering deployment, monitoring, error handling and security patterns; it runs Strands multi-agent systems
  - **AgentCore Identity**: granular, role-based permissions for each agent
  - **Amazon Bedrock Guardrails**: screens inputs and outputs, with multi-layered security and prompt hardening
  - **AgentCore Memory**: context across sessions and customer preferences
  - **AgentCore Observability**: logs every interaction so multi-step reasoning can be debugged

**Mobileye**

- Skilled engineers were spending their time answering status tickets: 66% of support tickets were routine status inquiries, and each ticket took about 15 clicks across several backend systems
- Context: 230M+ EyeQ chips deployed, with a data pipeline ingesting thousands of drive-recording sessions every day
- Why rule-based automation was not enough: scripts and decision trees handle predictable queries but not the variety of real requests
- **Hybrid design** where on-premises tickets meet a cloud agent:
  - On-premises: a local orchestrator pulls tickets and posts replies; the ticket system is not reachable from AWS
  - AWS AgentCore: the support agent runs on AgentCore Runtime, and credentials stay in Secrets Manager and are never exposed
  - Mobileye services: a data pipeline MCP server provides live status, logs and errors, and an LLM gateway serves Claude with quota management
  - AgentCore Observability traces each request through the MCP tool calls to the reply
  - There is no inbound path into the on-premises network, and live data reaches the model at inference time through MCP

#### Session 3: AI in Enterprise (Part 2) – Enterprise Challenges and Amazon Bedrock AgentCore

**Today's journey**

- **Duolingo case study**: why shared AI platforms matter
- **Amazon Bedrock AgentCore**: Strands, Runtime and the AgentCore map

### Key Takeaways

#### Production Mindset

- A prototype answers “does the model work?”, while production answers “does the system work for everyone, all the time, at a sustainable cost?”
- The model is one ingredient; the data pipeline, security, scaling, reliability, monitoring and cost matter just as much

#### Cloud Architecture

- Elastic services (Lambda, Auto Scaling, Load Balancer) fit changing demand better than fixed capacity
- Reliability comes from health checks, retries, failover and alarms
- Pay-per-use, right-sizing and caching keep costs under control

#### Enterprise Agents

- Standardizing the foundation first (runtime, identity, guardrails, memory, observability) lets many agents share the same safe base
- Hybrid designs can connect on-premises systems to cloud agents without opening inbound access
- MCP lets agents use live data at inference time

### Applying to Work

- **Think beyond the model** in my AI projects by planning the data pipeline, monitoring and cost from the start
- **Design for changing data and many users** instead of a single clean dataset
- **Use serverless and auto scaling** (Lambda, Auto Scaling, Load Balancer) for AI demos that may get unpredictable traffic
- **Add reliability basics** such as health checks, retries and alarms
- **Try Amazon Bedrock AgentCore** components (Runtime, Identity, Memory, Observability) for a small agent project
- **Keep credentials in Secrets Manager** and add guardrails to filter inputs and outputs

### Event Experience

Attending the **FPT University Workshop** helped me see how AI moves from a classroom prototype to a system that real users depend on.

#### Learning from speakers
- The restaurant analogy made abstract cloud and AI ideas easy to remember and compare.
- Hearing from a fresher AI engineer at FPT Software made the path from study to real projects feel reachable.

#### Real case studies
- Cox Automotive and Mobileye showed how large companies use AgentCore, guardrails and MCP to build agents that people can trust.
- The Mobileye case showed that automating routine work frees skilled engineers for harder problems.

#### Networking and discussions
- I had the chance to exchange ideas with FCAJ members, students and engineers who work with AI on the cloud.

#### Lessons learned
- Enterprise AI is judged by business value, reliability and trust, not accuracy alone.
- Standardizing a shared foundation makes it easier to scale many AI use cases safely.
- The cloud lets a small team handle infrastructure needs that once required a large operation.

#### Some event photos
![image event4](/fcj-workshop-template/images/4-EventParticipated/event4.jpg)

> Overall, the workshop gave me a clear picture of what it takes to turn an AI prototype into a secure, reliable and scalable product.
