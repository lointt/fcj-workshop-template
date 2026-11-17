---
title: "Worklog Tuần 9"
date: 2026-11-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Kiểm soát an toàn đầu vào/đầu ra của ứng dụng LLM bằng Amazon Bedrock Guardrails.
* Hiểu cách đưa xử lý AI/ML xuống thiết bị biên với AWS IoT Greengrass.
* Biết các cách chạy web app trên Lambda: Function URLs và Web Adapter.
* Nắm cách cân bằng tải với ALB và chạy container với Amazon ECS (Fargate/EC2).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Amazon Bedrock Guardrails**: lớp kiểm duyệt an toàn kiểm soát cả đầu vào (prompt) và đầu ra (response) cho ứng dụng LLM/Agents<br>&emsp;+ 6 cơ chế: Content Filters (hate speech, bạo lực, chặn Prompt Injection/Jailbreak), Denied Topics (cấm chủ đề nhạy cảm), Word Filters (từ tục tĩu, tên đối thủ), Sensitive Information Filters (block hoặc mask PII/Custom Regex như [EMAIL], [PHONE]), Contextual Grounding Checks (chống ảo giác RAG theo độ bám sát nguồn), Automated Reasoning Checks<br>&emsp;+ Ứng dụng: tích hợp vào Bedrock Models, Knowledge Bases, Bedrock Agents, hoặc gọi độc lập qua ApplyGuardrail API để bảo vệ cả model ngoài Bedrock | 9/11/2026 | 9/11/2026 | <https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html> |
| 3 | - **AWS IoT Greengrass**: dịch vụ đám mây và Edge Runtime mã nguồn mở, đưa khả năng xử lý của AWS xuống thiết bị biên<br>&emsp;+ Khả năng: xử lý dữ liệu cục bộ độ trễ thấp, hoạt động offline khi mất mạng, chạy suy luận AI/ML tại biên, cập nhật phần mềm/model từ xa (OTA) cho nhiều thiết bị<br>&emsp;+ Kiến trúc: đóng gói ứng dụng thành Greengrass Components (Lambda functions, Docker containers, Python scripts) -> triển khai từ Cloud xuống thiết bị cài Greengrass Core -> lọc dữ liệu tại chỗ, chỉ đẩy dữ liệu quan trọng/cảnh báo lên AWS IoT Core hoặc S3 qua Stream Manager | 10/11/2026 | 10/11/2026 | <https://docs.aws.amazon.com/greengrass/> |
| 4 | - **AWS Lambda Web Functions** (Lambda Function URLs & Lambda Web Adapter): chạy web app và HTTP API trực tiếp trên Lambda<br>&emsp;+ Lambda Function URLs: HTTPS endpoint riêng (https://<url-id>.lambda-url.<region>.on.aws) cho hàm Lambda, không cần API Gateway; hỗ trợ CORS, streaming response, 2 chế độ xác thực AWS_IAM hoặc NONE (public)<br>&emsp;+ Lambda Web Adapter (Lambda Layer / Container extension): chạy nguyên bản các web framework (Next.js, Express.js, FastAPI, Flask, Spring Boot) trên Lambda mà không phải sửa code theo chuẩn event handler | 11/11/2026 | 11/11/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/urls-configuration.html> |
| 5 | - **Amazon ALB (Application Load Balancer)**: bộ cân bằng tải tầng 7 (HTTP/HTTPS, gRPC, WebSockets) thuộc Elastic Load Balancing<br>&emsp;+ Thành phần: Listeners (port/protocol như 80, 443), Rules (định tuyến theo path /api/*, host, HTTP header, query string), Target Groups (EC2, ECS tasks/IPs, Lambda) cùng Health Checks tự động<br>&emsp;+ Tích hợp & bảo mật: chứng chỉ SSL/TLS miễn phí qua AWS Certificate Manager (SSL offloading), tích hợp AWS WAF chống tấn công web, hỗ trợ Sticky Sessions và xác thực qua Cognito hoặc OIDC | 12/11/2026 | 12/11/2026 | <https://docs.aws.amazon.com/elasticloadbalancing/latest/application/> |
| 6 | - **Amazon ECS (Elastic Container Service)**: dịch vụ điều phối và quản lý container của AWS<br>&emsp;+ Thành phần: Cluster (nhóm hạ tầng), Task Definition (bản thiết kế JSON khai báo Docker image, CPU/RAM, ports, IAM Task Role, CloudWatch logs), Task (instance chạy từ Task Definition), Service (giữ số Task mong muốn, tự phục hồi khi lỗi, gắn với ALB)<br>&emsp;+ 2 Launch Types: AWS Fargate (serverless, không quản lý máy chủ, tính phí theo vCPU và Memory thực dùng của Task) và Amazon EC2 (tự quản lý cụm EC2, tối ưu chi phí cho tải cố định hoặc dùng GPU) | 13/11/2026 | 13/11/2026 | <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/> |


### Kết quả đạt được tuần 9:

* Nắm 6 cơ chế của Bedrock Guardrails và cách dùng qua ApplyGuardrail API.
* Hiểu kiến trúc Greengrass: Components, Core device, Stream Manager, OTA và chạy offline.
* Phân biệt Lambda Function URLs với API Gateway và biết khi nào dùng Lambda Web Adapter.
* Hiểu Listener, Rule, Target Group, Health Check của ALB, cùng tích hợp ACM và WAF.
* Hiểu Cluster, Task Definition, Task, Service của ECS và khác biệt giữa Fargate với EC2 launch type.
