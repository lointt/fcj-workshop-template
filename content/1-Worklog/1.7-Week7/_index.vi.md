---
title: "Worklog Tuần 7"
date: 2026-10-26
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Học Infrastructure as Code với Terraform.
* Thiết lập CI/CD cho frontend bằng GitHub Actions.
* Làm quen Kiro Crew và thử dùng trong dự án.
* Nắm cơ bản ETL với AWS Glue và truy vấn dữ liệu bằng Athena.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu Terraform là gì (Infrastructure as Code) và luồng cơ bản: init, plan, apply, destroy<br>- Cài Terraform, cấu hình AWS provider và credentials<br>- Viết file .tf tạo VPC, subnet và S3 bucket<br>- Chạy plan/apply, kiểm tra kết quả trên console rồi destroy để đỡ tốn phí | 26/10/2026 | 26/10/2026 | <https://developer.hashicorp.com/terraform/tutorials/aws-get-started> |
| 3 | - Tìm hiểu cách GitHub Actions hoạt động: workflow, job, step, secrets<br>- Viết `.github/workflows/frontend.yml`: chạy khi push lên main, cài và build app React, upload bản build lên S3, invalidate cache CloudFront<br>- Lưu AWS key vào GitHub Secrets (sau đó thử dùng OIDC role)<br>- Push code để test pipeline và sửa lỗi theo log | 27/10/2026 | 27/10/2026 | <https://docs.github.com/en/actions> |
| 4 | - Tìm hiểu Kiro Crew là gì: workspace chạy agent liên tục xây trên Kiro, có memory lưu lâu dài, lập lịch và nhiều sub-agent<br>- Cài đặt, đọc cấu hình `.kiro` (steering, skills)<br>- Giao một task nhỏ trong dự án, xem nó làm việc và ghi nhớ những gì | 28/10/2026 | 28/10/2026 | <https://kiro.dev/docs/crew/> |
| 5 | - Tìm hiểu AWS Glue và ETL (extract, transform, load): Data Catalog, Crawler, Job<br>- Upload file CSV mẫu lên S3<br>- Tạo Crawler để tạo bảng trong Data Catalog<br>- Tạo Glue Job làm sạch/biến đổi dữ liệu rồi ghi lại S3 dạng Parquet | 29/10/2026 | 29/10/2026 | <https://docs.aws.amazon.com/glue/latest/dg/> |
| 6 | - Tìm hiểu Amazon Athena: chạy SQL serverless trên dữ liệu trong S3, dùng Glue Data Catalog<br>- Đặt vị trí lưu kết quả truy vấn trên S3<br>- Chạy các câu SELECT, WHERE, GROUP BY trên bảng từ Glue<br>- So sánh CSV và Parquet về lượng dữ liệu quét và chi phí | 30/10/2026 | 30/10/2026 | <https://docs.aws.amazon.com/athena/latest/ug/> |


### Kết quả đạt được tuần 7:

* Viết được file Terraform tạo VPC, subnet, S3 bucket và chạy được init/plan/apply/destroy.
* Viết xong frontend.yml, mỗi lần push lên main app React tự build và deploy lên S3 + CloudFront.
* Dùng thử Kiro Crew, hiểu cách memory, lịch chạy và sub-agent hoạt động.
* Làm được luồng ETL nhỏ: CSV trên S3, Glue Crawler, Glue Job ra Parquet.
* Truy vấn dữ liệu bằng Athena và thấy Parquet quét ít dữ liệu hơn CSV rõ rệt.
