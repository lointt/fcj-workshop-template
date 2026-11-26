---
title: "Worklog Tuần 11"
date: 2026-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Hoàn thiện triển khai đầu-cuối cho Workshop Website Thương mại điện tử Serverless và Chatbot RAG Full-Duplex.
* Kiểm thử 5 microservices backend, các worker bất đồng bộ EventBridge/SQS và tích hợp bên thứ ba (VNPay, GHN, Gmail SMTP).
* Kiểm thử Chatbot RAG Full-Duplex, đồng bộ CDC bằng DynamoDB Streams và luồng chuyển nhân viên hỗ trợ.
* Rà soát bảo mật, thiết lập giám sát CloudWatch và thực hành dọn dẹp tài nguyên sạch sẽ.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Triển khai & Kiểm thử Frontend SSR**:<br>&emsp;+ Build và deploy frontend Next.js 14 SSR lên S3 + Lambda SSR sau Amazon CloudFront và Edge WAF<br>&emsp;+ Kiểm tra phân phối ảnh sản phẩm từ S3, security headers và xác thực Cognito (đăng ký, đăng nhập, quên mật khẩu) | 23/11/2026 | 23/11/2026 | <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/> |
| 3 | - **Kiểm thử Backend Microservices & Hướng sự kiện**:<br>&emsp;+ Kiểm thử 5 microservices Lambda (`User`, `Catalog`, `Cart`, `Order`, `Payment Webhook`) qua REST API Gateway<br>&emsp;+ Xác nhận luồng thanh toán VNPay Sandbox và EventBridge → SQS → Workers (trừ kho, tạo vận đơn GHN Sandbox, gửi email qua Gmail SMTP) | 24/11/2026 | 24/11/2026 | <https://docs.aws.amazon.com/eventbridge/latest/userguide/> |
| 4 | - **Kiểm thử Chatbot RAG Full-Duplex & CDC**:<br>&emsp;+ Kiểm tra xác thực WebSocket API (`ChatAuthorizer`) cho cả khách vãng lai và khách đã đăng nhập Cognito<br>&emsp;+ Xác nhận đồng bộ DynamoDB Streams → `DynamoDBSyncToS3`, đề xuất sản phẩm trong khung chat và gửi email `HumanRequested` cho nhân viên | 25/11/2026 | 25/11/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api.html> |
| 5 | - **Siết bảo mật & Thiết lập giám sát**:<br>&emsp;+ Rà soát IAM Role theo nguyên tắc Least Privilege và kiểm tra phát hiện trên IAM Access Analyzer<br>&emsp;+ Cấu hình CloudWatch Logs, CloudWatch Alarms cho lỗi Lambda và cảnh báo email qua SNS | 26/11/2026 | 26/11/2026 | <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/> |
| 6 | - **Hoàn thiện tài liệu Workshop & Thực hành dọn dẹp**:<br>&emsp;+ Hoàn thiện hướng dẫn Workshop chi tiết (mục 5.1–5.5) kèm ảnh chụp màn hình và các bước kiểm thử<br>&emsp;+ Thực hành dọn dẹp toàn bộ: làm trống bucket S3 có versioning, chạy `terraform destroy` và xóa log CloudWatch, IAM còn sót | 27/11/2026 | 27/11/2026 | <https://developer.hashicorp.com/terraform/cli/commands/destroy> |

### Kết quả đạt được tuần 11:

* Kiểm thử hoàn chỉnh toàn bộ website thương mại điện tử Serverless và 5 microservices backend.
* Xác nhận luồng xử lý đơn hàng bất đồng bộ (trừ kho, giao vận GHN, thông báo Gmail) hoạt động ổn định với EventBridge, SQS và DLQ.
* Xác nhận Chatbot RAG trả lời thời gian thực, đồng bộ vector tự động qua DynamoDB Streams và chuyển tiếp nhân viên hỗ trợ thành công.
* Hoàn thiện tài liệu Workshop và xác nhận dọn dẹp sạch tài nguyên bằng `terraform destroy` để tránh phát sinh chi phí.
