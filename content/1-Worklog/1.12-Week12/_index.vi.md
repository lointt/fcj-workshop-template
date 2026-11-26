---
title: "Worklog Tuần 12"
date: 2026-11-26
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* Tìm hiểu truy vết phân tán với AWS X-Ray và rà soát dự án theo AWS Well-Architected Framework.
* Ước tính và tối ưu chi phí vận hành hàng tháng bằng AWS Pricing Calculator.
* Hoàn thiện các bài blog kỹ thuật, mục tự đánh giá, góp ý và xuất bản Báo cáo Thực tập hoàn chỉnh lên GitHub Pages.
* Chuẩn bị tài liệu tóm tắt, kịch bản demo và tập duyệt cho buổi báo cáo cuối kỳ.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **AWS X-Ray & Truy vết phân tán (Distributed Tracing)**:<br>&emsp;+ Tìm hiểu cách X-Ray theo dõi request xuyên suốt qua API Gateway, Lambda, DynamoDB và SQS<br>&emsp;+ Nắm khái niệm Service Map, Segment, Subsegment và cách tìm điểm nghẽn độ trễ trong ứng dụng serverless | 30/11/2026 | 30/11/2026 | <https://docs.aws.amazon.com/xray/latest/devguide/aws-xray.html> |
| 3 | - **Rà soát theo AWS Well-Architected Framework**:<br>&emsp;+ Đánh giá kiến trúc dự án theo 6 trụ cột: Vận hành xuất sắc, Bảo mật, Độ tin cậy, Hiệu năng, Tối ưu chi phí và Bền vững<br>&emsp;+ Ghi nhận các đánh đổi kiến trúc và hướng mở rộng trong tương lai (multi-region DR, xoay vòng secret tự động) | 01/12/2026 | 01/12/2026 | <https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html> |
| 4 | - **Ước tính chi phí & Hoàn thiện Blog kỹ thuật**:<br>&emsp;+ Hoàn tất bảng dự toán trên AWS Pricing Calculator (~5,14 USD/tháng cho 1.000 người dùng) và xuất tệp `Cost_Estimate.csv`<br>&emsp;+ Hoàn thiện và đăng tải các bài blog kỹ thuật (Bedrock AgentCore, IAM Access Analyzer, Rekognition + Athena) | 02/12/2026 | 02/12/2026 | <https://calculator.aws/> |
| 5 | - **Hoàn thiện Báo cáo Thực tập (Hugo & GitHub Pages)**:<br>&emsp;+ Hoàn tất đầy đủ các mục song ngữ (EN/VI): Worklog, Proposal, Blogs, Events, Workshop, Tự đánh giá và Chia sẻ/Góp ý<br>&emsp;+ Kiểm tra build Hugo qua GitHub Actions, rà soát toàn bộ liên kết nội bộ và hình ảnh trên GitHub Pages | 03/12/2026 | 03/12/2026 | <https://gohugo.io/documentation/> |
| 6 | - **Chuẩn bị báo cáo cuối kỳ & Tập duyệt Demo**:<br>&emsp;+ Soạn tài liệu tóm tắt dự án (Problem Statement, Proposed Solution, End-to-End Workflow, Security/Monitoring, Cost)<br>&emsp;+ Tập duyệt demo trực tiếp và chuẩn bị phần hỏi đáp để kết thúc kỳ thực tập First Cloud AI Journey | 04/12/2026 | 04/12/2026 | <https://hcm-rules.awsfcaj.com/5-scoring/> |

### Kết quả đạt được tuần 12:

* Hiểu cách truy vết phân tán bằng AWS X-Ray và đánh giá được dự án theo 6 trụ cột của AWS Well-Architected Framework.
* Hoàn thiện bảng dự toán chi phí chi tiết (~5,14 USD/tháng) và đăng tải đầy đủ các bài blog kỹ thuật.
* Xuất bản hoàn chỉnh Báo cáo Thực tập song ngữ lên GitHub Pages với đầy đủ liên kết, hình ảnh và CI/CD tự động.
* Chuẩn bị xong tài liệu tổng kết và tập duyệt hoàn chỉnh phần demo dự án cuối kỳ.
