---
title: "Worklog Tuần 2"
date: 2026-09-21
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu tuần 2:

* Nắm vững kiến thức mạng cơ bản trên AWS: VPC, subnet, Internet Gateway, route table, security group và VPC Flow Logs.
* Thực hành triển khai và quản lý máy chủ EC2 (Linux), snapshot và AMI.
* Làm quen với Cloud9 và các câu lệnh Linux/AWS CLI cơ bản.
* Triển khai static website với S3 và tăng tốc bằng CloudFront.
* Tạo và quản lý cơ sở dữ liệu MySQL trên Amazon RDS, kết nối với ứng dụng chạy trên EC2.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - VPC:<br>&emsp;+ Tạo VPC<br>&emsp;+ Tạo Subnet: Public Subnet 1, Public Subnet 2, Private Subnet 1, Private Subnet 2<br>&emsp;+ Tạo Internet GateWay<br>&emsp;+ Tạo Route Table: Route table-Public<br>&emsp;+ Tạo Security Group: Public subnet - SG, Private subnet - SG, VPC-Endpoints-SG<br>&emsp;+ Bật VPC Flow Logs để xem Flow Logs trong CloudWatch<br>&emsp;                                                                                          | 21/09/2026   | 21/09/2026      | <https://000003.awsstudygroup.com/3-prerequisite/> |
| 3   | - EC2:<br>&emsp;+ Khởi chạy linux-instance<br>&emsp;+ Điều khiển máy chủ từ xa: MobaXterm, PuTTY<br>&emsp;+ Thay đổi loại Instance<br>&emsp;+ Tạo snapshot<br>&emsp;+ Tạo và chạy AMI (image);                                             | 22/09/2026   | 22/09/2026      | <https://000004.awsstudygroup.com/4-launchlinuxinstance/> |
| 4   | - Cloud9: <br>&emsp; + câu lệnh cơ bản: pwd, ls -la, mkdir, cd, touch test.txt, vi test.txt, :wq, cat test.txt<br>&emsp;+ CLI: aws --version, aws s3 ls, aws ec2 describe-instances| 23/09/2026   | 23/09/2026      | <https://000049.awsstudygroup.com/1-createcloudshell/> |
| 5   | - S3 và Cloudfont:<br>&emsp;+ tạo S3 bucket and tải data<br>&emsp;+ Enable static website hosting (at properties)<br>&emsp;+ tắt: block all public access (at permission)<br>&emsp;+ ACLs enabled (at permission)<br>&emsp;+ mở S3 endpoint (at properties)<br>&emsp;+ gia tốc Static Websites với Cloudfront:<br>&emsp;  - bật: block all public access <br>&emsp;  - Cloudfront: tạo distribution, nhập index.html vào Default root object, sao chép policy trong origin và dán vào Bucket policy<br>&emsp;  - mở Cloudfront endpoint<br>&emsp;                          | 24/09/2026 | 24/09/2026      | <https://000057.awsstudygroup.com/3-staticwebsite/> |
| 6   | - Aurora and RDS:<br>&emsp;+ tạo MySQL<br>&emsp;  + khởi chạy EC2 instance<br>&emsp;+ kết nối instance đến MobaXterm<br>&emsp;+ kết nối MySQL đến MobaXterm<br>&emsp;+ triển khai ứng dụng <br>&emsp;+ tương tác dashboard MySQL (view, edit, delete)<br>&emsp;+ Bảo trì và sao lưu MySQL                                                                                      | 25/09/2026 | 25/09/2026      | <https://000005.awsstudygroup.com/3-create-rds/> |


### Kết quả đạt được tuần 2:

* Tạo VPC với 2 public subnet, 2 private subnet, Internet Gateway, route table và các security group (Public, Private, VPC Endpoints); bật VPC Flow Logs để xem trong CloudWatch.
* Khởi chạy EC2 Linux instance, điều khiển từ xa bằng MobaXterm/PuTTY, đổi loại instance, tạo snapshot và AMI.
* Sử dụng Cloud9 với các câu lệnh Linux cơ bản và AWS CLI (aws --version, aws s3 ls, aws ec2 describe-instances).
* Tạo S3 bucket, bật static website hosting, và tăng tốc website bằng CloudFront distribution kèm bucket policy.
* Tạo cơ sở dữ liệu MySQL trên RDS, kết nối từ EC2 qua MobaXterm, triển khai ứng dụng, thao tác dữ liệu và thực hành bảo trì, sao lưu.
