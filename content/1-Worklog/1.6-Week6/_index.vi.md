---
title: "Worklog Tuần 6"
date: 2026-10-19
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Hiểu khái niệm Amazon Bedrock, Bedrock AgentCore, SageMaker AI, AWS Continuum và AWS RAM.
* Xin quyền truy cập các mô hình AI trong Bedrock cho tài khoản Free Tier và gọi mô hình từ console và SDK.
* Xây dựng và triển khai một AI agent đơn giản với Bedrock AgentCore.
* Thực hành quy trình ML cơ bản trên SageMaker AI: notebook, huấn luyện và triển khai mô hình.
* Tìm hiểu bảo mật mã nguồn bằng AI với Continuum và chia sẻ tài nguyên giữa các tài khoản với RAM.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Khái niệm Amazon Bedrock: dịch vụ được quản lý để truy cập các foundation model (FM) qua một API thống nhất; Model catalog, Playground, API `InvokeModel` và `Converse`<br>- Gửi yêu cầu xin quyền sử dụng các mô hình AI cho tài khoản Free Tier:<br>&emsp;+ Mở mô hình trong Bedrock playground / Model catalog để bắt đầu cấp quyền truy cập<br>&emsp;+ Với mô hình Anthropic, điền form use case (một lần) và chờ trạng thái chuyển từ PENDING sang AVAILABLE<br>&emsp;+ Cấp cho IAM identity các quyền AWS Marketplace cần thiết cho lần dùng đầu tiên của mô hình bên thứ ba<br>- Thực hành: trò chuyện với mô hình đã được cấp quyền trong Playground và gọi mô hình bằng `boto3` (`bedrock-runtime`, `converse`) | 19/10/2026 | 19/10/2026 | <https://docs.aws.amazon.com/bedrock/latest/userguide/model-access.html> |
| 3 | - Khái niệm Amazon Bedrock AgentCore: nền tảng xây dựng, triển khai và vận hành AI agent an toàn ở quy mô lớn; các thành phần chính: Runtime, Memory, Gateway, Identity, Observability, Code Interpreter, Browser<br>- Thực hành:<br>&emsp;+ Tạo IAM role/quyền cho AgentCore<br>&emsp;+ Viết một agent đơn giản và triển khai lên AgentCore Runtime<br>&emsp;+ Gọi agent và xem log/trace trong CloudWatch<br>&emsp;+ Thử AgentCore Memory để lưu ngữ cảnh hội thoại<br>&emsp;+ Xóa tài nguyên sau khi thực hành để tránh phát sinh chi phí | 20/10/2026 | 20/10/2026 | <https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/> |
| 4 | - Khái niệm Amazon SageMaker AI: nền tảng ML được quản lý để xây dựng, huấn luyện và triển khai mô hình; Studio, notebook, training job, endpoint, JumpStart<br>- Thực hành:<br>&emsp;+ Tạo SageMaker domain và mở Studio (với execution role và S3 bucket)<br>&emsp;+ Chạy notebook: tải dataset mẫu, huấn luyện một mô hình đơn giản và xem kết quả<br>&emsp;+ Thử SageMaker JumpStart: triển khai mô hình huấn luyện sẵn lên real-time endpoint và kiểm tra suy luận<br>&emsp;+ Xóa endpoint, app và domain sau khi thực hành để tránh phát sinh chi phí | 21/10/2026 | 21/10/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/> |
| 5 | - Khái niệm AWS Continuum: nền tảng bảo mật dùng AI (ra mắt tháng 6/2026) để tìm, xác thực và đề xuất cách sửa lỗ hổng phần mềm; bốn giai đoạn: nạp/quét, ưu tiên, xác thực trong sandbox, đề xuất bản sửa; chế độ learn (có con người giám sát) và enforce (tự động khắc phục); gồm Continuum code scanning, pen testing và threat modeling (preview)<br>- Thực hành: tính năng quét lỗ hổng mã nguồn của Continuum đang ở dạng gated preview, nên đăng ký quyền truy cập và tìm hiểu quy trình, cách tiếp cận chế độ learn và mối liên hệ với thực hành bảo mật IAM, CloudWatch | 22/10/2026 | 22/10/2026 | <https://aws.amazon.com/continuum/> |
| 6 | - Khái niệm AWS Resource Access Manager (RAM): chia sẻ tài nguyên AWS cho tài khoản khác, tổ chức hoặc OU mà không cần nhân bản; resource share, principal, managed permission<br>- Thực hành:<br>&emsp;+ Tạo resource share (ví dụ một VPC subnet)<br>&emsp;+ Thêm principal (tài khoản AWS khác hoặc AWS Organization) và chọn managed permission<br>&emsp;+ Chấp nhận lời mời ở tài khoản nhận và kiểm tra tài nguyên được chia sẻ<br>&emsp;+ Xóa resource share sau khi thực hành | 23/10/2026 | 23/10/2026 | <https://docs.aws.amazon.com/ram/latest/userguide/> |


### Kết quả đạt được tuần 6:

* Hiểu Amazon Bedrock và đã gửi yêu cầu xin quyền sử dụng các mô hình AI cho tài khoản Free Tier (gồm form use case của Anthropic), sau đó dùng mô hình trong Playground và qua `boto3`.
* Hiểu các thành phần của Bedrock AgentCore và triển khai một agent đơn giản lên AgentCore Runtime, kèm log/trace và memory.
* Hiểu SageMaker AI và thực hành tạo domain, chạy notebook, huấn luyện mô hình đơn giản, triển khai mô hình JumpStart lên endpoint, sau đó dọn dẹp tài nguyên.
* Hiểu quy trình AWS Continuum (quét, ưu tiên, xác thực, sửa lỗi) cùng chế độ learn/enforce và đã đăng ký quyền truy cập gated preview.
* Hiểu AWS RAM và chia sẻ một tài nguyên (VPC subnet) cho tài khoản khác, sau đó kiểm tra từ tài khoản nhận.
* Biết dọn dẹp tài nguyên sau mỗi bài lab để kiểm soát chi phí trên Free Tier.
