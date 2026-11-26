---
title: "Worklog Tuần 10"
date: 2026-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Tìm hiểu các dịch vụ AI quản lý sẵn cho ảnh và văn bản: Amazon Rekognition, Amazon Textract và Amazon Comprehend.
* Kết hợp Amazon Rekognition với Amazon Athena để truy vấn kết quả phân tích ảnh bằng SQL.
* Nắm cách quản lý bí mật và mã hóa trên AWS với AWS Secrets Manager và AWS KMS.
* Tìm hiểu điều phối luồng xử lý serverless với AWS Step Functions.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Amazon Rekognition**: dịch vụ phân tích ảnh và video bằng deep learning<br>&emsp;+ Thử nghiệm `DetectLabels` qua AWS CLI trên 30 ảnh từ bộ dữ liệu Imagenette lưu trên S3<br>&emsp;+ So sánh ngưỡng `MinConfidence` (80 và 55) để thấy sự đánh đổi giữa độ phủ và độ chính xác<br>&emsp;+ Gộp kết quả JSON lên S3 và dùng Amazon Athena chạy SQL thống kê nhãn | 16/11/2026 | 16/11/2026 | <https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html> |
| 3 | - **Amazon Textract**: trích xuất văn bản, biểu mẫu và bảng từ tài liệu scan và PDF<br>&emsp;+ Phân biệt API đồng bộ (`DetectDocumentText`, `AnalyzeDocument`) và bất đồng bộ cho PDF nhiều trang<br>&emsp;+ Tìm hiểu ứng dụng xử lý hóa đơn và số hóa danh mục sản phẩm | 17/11/2026 | 17/11/2026 | <https://docs.aws.amazon.com/textract/latest/dg/what-is.html> |
| 4 | - **Amazon Comprehend**: dịch vụ xử lý ngôn ngữ tự nhiên (NLP)<br>&emsp;+ Tìm hiểu các tính năng: phân tích cảm xúc (Sentiment Analysis), nhận diện thực thể, trích xuất cụm từ khóa và phát hiện PII<br>&emsp;+ Xem xét cách dùng Comprehend để phân loại phản hồi khách hàng | 18/11/2026 | 18/11/2026 | <https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html> |
| 5 | - **AWS Secrets Manager & AWS KMS**: quản lý thông tin bí mật và khóa mã hóa<br>&emsp;+ Lưu các API key và thông tin xác thực (Gemini API, VNPay, GHN, Gmail SMTP) trong Secrets Manager thay vì để cứng trong biến môi trường Lambda<br>&emsp;+ Hiểu khóa đối xứng KMS, mã hóa phong bì (envelope encryption) và key policy | 19/11/2026 | 19/11/2026 | <https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html> |
| 6 | - **AWS Step Functions**: điều phối luồng công việc trực quan cho ứng dụng serverless<br>&emsp;+ Tìm hiểu Amazon States Language (ASL), các trạng thái Task/Choice/Parallel và xử lý lỗi (`Retry`, `Catch`)<br>&emsp;+ Phân biệt Standard Workflows (chạy dài, thực thi đúng một lần) và Express Workflows (tải cao, thời gian ngắn) | 20/11/2026 | 20/11/2026 | <https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html> |

### Kết quả đạt được tuần 10:

* Chạy thành công quy trình phân tích ảnh với Amazon Rekognition `DetectLabels`, S3 và truy vấn SQL trên Amazon Athena.
* Hiểu cách Amazon Textract trích xuất bảng/biểu mẫu và cách Amazon Comprehend phân tích cảm xúc, thực thể trong văn bản.
* Áp dụng AWS Secrets Manager và KMS để bảo vệ các khóa API bên thứ ba.
* Nắm được cấu trúc state machine của AWS Step Functions, cơ chế `Retry`/`Catch` và khi nào chọn Standard hay Express workflow.
