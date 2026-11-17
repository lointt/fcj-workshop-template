---
title: "Worklog Tuần 8"
date: 2026-11-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Biết đánh giá chất lượng ứng dụng RAG bằng Amazon Bedrock Evaluation.
* Nắm cách giám sát và kiểm toán hoạt động tài khoản AWS với CloudTrail và GuardDuty.
* Tìm hiểu Amazon Q Business để xây trợ lý AI nội bộ cho doanh nghiệp.
* Áp dụng nguyên tắc Least Privilege với IAM Access Analyzer.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Amazon Bedrock Evaluation**: đánh giá chất lượng ứng dụng RAG<br>&emsp;+ 2 chế độ đánh giá: "Retrieve only" và "Retrieve and Generate"<br>&emsp;+ Chỉ số của "Retrieve only": context relevance, context coverage<br>&emsp;+ Chỉ số của "Retrieve and Generate": correctness, completeness, helpfulness, logical coherence...<br>&emsp;+ Quy trình: chuẩn bị bộ câu hỏi/câu trả lời (JSONL) -> tải lên S3 -> trên Bedrock console chọn nguồn RAG, chế độ đánh giá, mô hình giám khảo, chỉ số đánh giá, mô hình tạo câu trả lời -> xem báo cáo kết quả | 2/11/2026 | 2/11/2026 | <https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation.html> |
| 3 | - **AWS CloudTrail**:<br>&emsp;+ Ghi nhận thay đổi từ AWS Management Console, AWS CLI, AWS SDKs & APIs và các tác vụ tự động nội bộ của AWS<br>&emsp;+ Event types: Management Events, Data Events, Insights Events (định dạng JSON)<br>&emsp;+ Lưu trữ: "Event History" chỉ giữ Management Events trong 90 ngày; dùng "Trails" để nén .json.gz sang Amazon S3 bucket nếu cần lưu quá 90 ngày | 3/11/2026 | 3/11/2026 | <https://docs.aws.amazon.com/awscloudtrail/latest/userguide/> |
| 4 | - **AWS GuardDuty**: phát hiện mối đe dọa thông minh bằng Machine Learning<br>&emsp;+ Dữ liệu đầu vào: CloudTrail Events, VPC Flow Logs, DNS Query Logs<br>&emsp;+ Mức độ Findings: Low, Medium, High<br>&emsp;+ Định dạng chuẩn: ThreatPurpose:ResourceType/ThreatFamilyName.DetectionMechanism<br>&emsp;+ Finding thường gặp: CryptoCurrency:EC2/BitcoinTool.B!DNS; UnauthorizedAccess:IAMUser/InstanceCredentialExfiltration.OutsideAWS | 4/11/2026 | 4/11/2026 | <https://docs.aws.amazon.com/guardduty/latest/ug/> |
| 5 | - **Amazon Q Business**: trợ lý Generative AI cho doanh nghiệp dựa trên dữ liệu nội bộ (Enterprise RAG)<br>&emsp;+ Thành phần cốt lõi: Data Sources (40+ connector: S3, SharePoint, Jira, Confluence, Slack...), Index (lập chỉ mục ngữ nghĩa), Retriever và Plugins (thực thi tác vụ trên hệ thống bên thứ 3)<br>&emsp;+ Bảo mật & phân quyền: tích hợp AWS IAM Identity Center, kiểm soát truy cập cấp tài liệu bằng ACLs, user chỉ nhận câu trả lời từ tài liệu họ có quyền xem<br>&emsp;+ Quy trình: tạo Application -> kết nối IAM Identity Center -> thêm Data Source & Sync vào Index -> cấu hình Guardrails/Admin Controls -> triển khai Web Experience cho người dùng cuối | 5/11/2026 | 5/11/2026 | <https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/> |
| 6 | - **IAM Access Analyzer**: phân tích chính sách bằng Automated Reasoning và tinh chỉnh quyền theo chuẩn Least Privilege<br>&emsp;+ 4 tính năng: External Access Analysis (phát hiện tài nguyên chia sẻ ra ngoài Zone of Trust, miễn phí), Unused Access Analysis (quét role/user/access key bị bỏ quên, tính phí), Policy Validation (kiểm tra cú pháp và hơn 100 quy tắc bảo mật), Policy Generation (tự sinh JSON policy từ lịch sử hoạt động thực tế)<br>&emsp;+ Quy trình Least Privilege: bật CloudTrail Trail (Management + Data Events) và chạy test ở Dev -> Generate policy trong IAM Role để quét log CloudTrail -> giới hạn Resource ARN và kiểm tra bằng Policy Validation -> gắn policy chuẩn lên Production và bật External Access Analyzer để giám sát | 6/11/2026 | 6/11/2026 | <https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html> |


### Kết quả đạt được tuần 8:

* Nắm quy trình đánh giá RAG của Bedrock Evaluation: 2 chế độ, các chỉ số và cách đọc báo cáo.
* Hiểu CloudTrail ghi lại những loại event nào và cách lưu log quá 90 ngày bằng Trails + S3.
* Hiểu cách GuardDuty phân tích log để phát hiện mối đe dọa, cách đọc mức độ và tên Finding.
* Nắm kiến trúc Amazon Q Business: Data Sources, Index, Retriever, Plugins và phân quyền bằng IAM Identity Center + ACLs.
* Nắm 4 tính năng của IAM Access Analyzer và quy trình sinh policy Least Privilege từ log CloudTrail.
