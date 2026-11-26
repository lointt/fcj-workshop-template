---
title: "Các bài blogs đã đăng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Tại đây là danh sách và phần giới thiệu các bài blog kỹ thuật tôi đã đăng trên [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj) trong quá trình thực tập.

### [Blog 1 - Amazon Bedrock AgentCore: Hạ tầng còn thiếu để đưa AI Agent vào Production](3.1-blog1/)
Giới thiệu **Amazon Bedrock AgentCore**, nền tảng dạng module, không khóa framework của AWS giúp triển khai và vận hành AI agent ở quy mô production. Bài viết trình bày các thành phần chính (Runtime, Memory, Gateway, Identity, Code Interpreter/Browser, Observability, Evaluations và Policy với Cedar) kèm hướng dẫn thực hành nhanh bằng AgentCore CLI.

### [Blog 2 - AWS IAM Access Analyzer: Siết quyền Least Privilege chuẩn chỉnh!](3.2-blog2/)
Chia sẻ cách **AWS IAM Access Analyzer** ứng dụng Automated Reasoning để phát hiện tài nguyên chia sẻ ra ngoài và siết quyền theo nguyên tắc Đặc quyền tối thiểu (Least Privilege). Trình bày quy trình 5 bước từ Dev lên Production kết hợp CloudTrail Data Events, Policy Generation, Policy Validation, External Access Analyzer và Unused Access Analyzer, kèm ví dụ JSON trước/sau thực tế.

### [Blog 3 - Amazon Rekognition kết hợp Amazon Athena: Phân tích ảnh bằng AI và truy vấn bằng SQL](3.3-blog3/)
Hướng dẫn kết hợp **Amazon Rekognition** (`DetectLabels`) và **Amazon Athena** để tự động gắn nhãn ảnh lưu trên S3 và thống kê kết quả bằng SQL. Bài viết ghi lại thử nghiệm thực tế trên 30 ảnh Imagenette, so sánh ngưỡng `MinConfidence` (80 và 55), phân tích chi phí và các lưu ý về IAM, quyền riêng tư.
