---
title: "Worklog Tuần 5"
date: 2026-10-12
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Xây dựng nền tảng mạng riêng trên AWS: VPC, subnet, gateway, route table và VPC endpoint.
* Triển khai Amazon OpenSearch trong private subnet làm kho tìm kiếm/vector cho chatbot.
* Đồng bộ dữ liệu từ DynamoDB sang OpenSearch theo thời gian thực bằng DynamoDB Streams.
* Xây dựng backend chatbot AI bằng Lambda, truy xuất dữ liệu từ OpenSearch và gọi Gemini API.
* Cho phép chat hai chiều theo thời gian thực giữa frontend và backend với API Gateway (WebSocket API).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tạo VPC<br>- Thêm 4 subnet: Public AZ1, Public AZ2, Private AZ1, Private AZ2<br>- Tạo Internet Gateway<br>- Tạo NAT Gateway để các Private Subnet kết nối ra ngoài internet<br>- Cấu hình Public Route Table (route tới IGW)<br>- Cấu hình Private Route Table (route tới NAT Gateway) | 12/10/2026 | 12/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Tạo Gateway Endpoint cho DynamoDB<br>- Tạo Security Group cho Interface Endpoint: Interface Endpoint tạo ENI trực tiếp trong private subnet, vì vậy dùng security group để kiểm soát luồng traffic<br>- Tạo Interface Endpoint cho AWS Secrets Manager | 13/10/2026 | 13/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Tạo OpenSearch Domain:<br>&emsp;+ Tạo Security Group cho OpenSearch<br>&emsp;+ Tạo OpenSearch Domain bên trong private subnet của VPC<br>&emsp;+ Chọn 1-AZ, 1 data node, t3.small.search, loại EBS volume: General Purpose (SSD) - gp3, dung lượng EBS mỗi node: 10 GiB để tiết kiệm chi phí trong giai đoạn phát triển/kiểm thử | 14/10/2026 | 14/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Tạo Lambda function chạy một lần để tạo vector index cho OpenSearch<br>- Tạo Lambda DynamoDBSyncToOS: dùng DynamoDB Streams để ghi nhận thay đổi dữ liệu theo thời gian thực từ DynamoDB và đồng bộ sang OpenSearch<br>- Tạo Lambda ChatOrchestratorHandler: truy vấn OpenSearch và gọi Gemini API để trả lời khách hàng | 15/10/2026 | 15/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - Cấu hình Amazon API Gateway (WebSocket API):<br>&emsp;+ $connect: khi frontend mở kết nối WebSocket, API Gateway tạo một `connectionId` duy nhất<br>&emsp;+ $disconnect: được kích hoạt khi frontend đóng tab hoặc mất kết nối mạng<br>&emsp;+ sendMessage: nhận tin nhắn chat từ client và kích hoạt `ChatOrchestratorHandler`<br>&emsp;+ Giao tiếp hai chiều: vì xử lý AI trong Lambda có thể mất vài giây, thay vì chờ HTTP response, Lambda dùng SDK `boto3.client('apigatewaymanagementapi')` để đẩy phản hồi về đúng `connectionId` của client | 16/10/2026 | 16/10/2026 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 5:

* Tạo VPC với 2 public subnet và 2 private subnet trên 2 AZ, Internet Gateway và NAT Gateway, cấu hình đúng public/private route table.
* Tạo Gateway Endpoint cho DynamoDB và Interface Endpoint cho AWS Secrets Manager, dùng Security Group kiểm soát traffic, giúp tài nguyên private truy cập dịch vụ AWS mà không đi qua internet công cộng.
* Triển khai Amazon OpenSearch Domain trong private subnet (1 AZ, 1 node t3.small.search, 10 GiB gp3) cùng Security Group riêng, tối ưu chi phí cho giai đoạn phát triển/kiểm thử.
* Tạo Lambda chạy một lần để tạo vector index cho OpenSearch và Lambda DynamoDBSyncToOS đồng bộ thay đổi từ DynamoDB sang OpenSearch qua DynamoDB Streams.
* Tạo Lambda ChatOrchestratorHandler sử dụng OpenSearch để truy xuất và Gemini API để trả lời câu hỏi của khách hàng.
* Cấu hình API Gateway (WebSocket API) với các route $connect, $disconnect, sendMessage và đẩy phản hồi AI về đúng connectionId của từng client để giao tiếp hai chiều theo thời gian thực.
