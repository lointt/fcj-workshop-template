---
title: "Worklog Tuần 4"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---


### Mục tiêu tuần 4:

* Xây dựng nền tảng website thương mại điện tử serverless trên AWS (phụ tùng xe máy).
* Triển khai xác thực người dùng với Amazon Cognito (JWT) và giao diện React trên S3 + CloudFront.
* Thiết kế backend serverless: DynamoDB, Lambda, API Gateway.
* Xây dựng luồng xử lý đơn hàng bất đồng bộ với SNS, SQS và EventBridge.
* Kết nối Frontend với Backend để lấy dữ liệu thực tế từ DynamoDB.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Amazon Cognito: Quản lý đăng ký, đăng nhập, và nhận JWT token cho users và admins.<br>- Tạo User Pool: <br>&emsp;+ Tùy chọn sign-in identifier: Email<br>&emsp;+ chọn attributes: name and phone_number<br>&emsp;+ URL: điền Cloudfront Distribution URL<br>- Lấy Thông tin Cấu hình cho Frontend:<br>&emsp;+ User Pool ID<br>&emsp;+ App Client ID | 5/10/2026   | 5/10/2026      | <https://awsstudygroup.com/> |
| 3   | - Tạo giao diện React và tải lên S3; kết nối với Cognito; triển khai trên CloudFront:<br>&emsp;+ Khởi tạo dự án React: npx create-react-app phutungxemay<br>&emsp;+ Cài đặt thư viện AWS Amplify để kết nối với Cognito: npm install aws-amplify @aws-amplify/ui-react<br>&emsp;+ Thêm tệp cấu hình kết nối AWS Cognito: src/aws-exports.js<br>&emsp;+ Tạo giao diện đơn giản E-commerce + Auth: src/App.js<br>&emsp;+ Đóng gói dự án thành các tệp tĩnh và tải lên S3: npm run build<br>&emsp;+ Kiểm tra trên tên miền CloudFront: https://xxxxxxxxx.cloudfront.net | 6/10/2026   | 6/10/2026      | <https://awsstudygroup.com/> |
| 4   | - Tạo các bảng DynamoDB: CatalogDB và OrdersDB<br>- Tạo IAM Role cho các hàm Lambda<br>- Khởi tạo các hàm Lambda:<br>&emsp;+ Read/WriteCatalogLambda để đọc/ghi dữ liệu sản phẩm trong DynamoDB<br>&emsp;+ Cart/OrderLambda để thêm sản phẩm vào cart và lưu thông tin order<br>&emsp;+ PaymentWebhookLambda để nhận webhooks từ MoMo/VNPay payment gateways.<br>&emsp;+ InventoryShippingWorkerLambda để quản lý inventory và kết nối API vận chuyển bên thứ 3<br>&emsp;+ Thêm trigger để kết nối SQS trong InventoryShippingWorkerLambda   | 7/10/2026      | 7/10/2026      | <https://awsstudygroup.com> |
| 5   | - Tạo Amazon SNS Topic (Thông báo Email)<br>- Tạo Amazon SQS Queue (xử lý Order)<br>- Cấu hình Amazon EventBridge (Event Bus)<br>&emsp;+ Tạo Subscriber cho SQS <br>&emsp;+ Tạo Subscriber cho SNS                           | 8/10/2026 | 8/10/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Khởi tạo Amazon API Gateway (REST API):<br>&emsp;+ Tạo Authorizer với Cognito (bảo mật JWT)<br>&emsp;+ Tạo Resource:  /products, /orders,  /webhook/payment<br>&emsp;+ Tạo Method: GET, POST, POST<br>&emsp;+ Bật CORS tại /products: Access-Control-Allow-Methods: Tick chọn GET, OPTIONS<br>&emsp;+ nhấn Deploy API<br>- Kết nối Frontend và Backend để lấy dữ liệu thực tế từ DynamoDB (CatalogDB) thông qua API Gateway và Lambda                                                                                      | 9/10/2026 | 9/10/2026      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 4:

* Tạo User Pool trên Amazon Cognito (đăng nhập bằng Email, thuộc tính name và phone_number) và lấy được User Pool ID, App Client ID để cấu hình cho Frontend.
* Xây dựng giao diện React (E-commerce + Auth) bằng AWS Amplify, build thành tệp tĩnh, tải lên S3 và phân phối qua CloudFront.
* Tạo các bảng DynamoDB (CatalogDB, OrdersDB), IAM Role và các hàm Lambda xử lý catalog, giỏ hàng/đơn hàng, webhook thanh toán (MoMo/VNPay), tồn kho và vận chuyển.
* Cấu hình SNS Topic (thông báo email), SQS Queue (xử lý đơn hàng) và EventBridge Event Bus với các subscriber tương ứng, kết nối trigger SQS cho Lambda.
* Khởi tạo API Gateway (REST API) với Cognito Authorizer, các resource /products, /orders, /webhook/payment, bật CORS và deploy API.
* Kết nối thành công Frontend với Backend, hiển thị dữ liệu sản phẩm thực tế từ DynamoDB thông qua API Gateway và Lambda.
