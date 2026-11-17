---
title: "Worklog Tuần 3"
date: 2026-09-28
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---


### Mục tiêu tuần 3:

* Triển khai website WordPress/WooCommerce trên Amazon Lightsail và gắn tên miền riêng.
* Cài đặt chứng chỉ SSL (certbot) với tự động gia hạn và chuyển hướng HTTP sang HTTPS.
* Thiết lập sao lưu tự động (Auto Snapshot) và chuyển quản lý DNS sang Amazon Route 53.
* Tối ưu lưu trữ media của WordPress bằng S3 và CloudFront.
* Biết vẽ sơ đồ kiến trúc AWS trên draw.io.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Lightsail:<br>&emsp;+ Tạo instance với Wordpress blueprint<br>&emsp;+ Gán địa chỉ IP tĩnh (cố định địa chỉ IP tĩnh)<br>&emsp;+ Đăng nhập wordPress Admin: kết nối sử dụng SSH, lấy username and password, http://[fixed static IP]/wp-admin<br>&emsp; + Chọn và chỉnh sửa website template: plugin woocommerce, theme - Astra, Plugin Starter Templates - E-Commerce, chuyển coming soon -> live, cài đặt Payments<br>&emsp; + Mua tên miền (NameCheap) and gán DNS (Account - Domain List - Advanced DNS): A record - @ - Your static IP - Automatic, A record - www - Your static IP - Automatic<br>&emsp;                                                                                           | 28/09/2026 | 28/09/2026      | <https://000045.awsstudygroup.com/2-wp-instance/2.1-deploy-instance/> |
| 3   | - Tạo chứng chỉ SSL bằng bncert-tool bị lỗi:<br>&emsp;+ WordPress mới, Bitnami đã bỏ hẳn mô hình Monolithic cũ.<br>&emsp;+ File properties.ini và ctlscript.sh đã bị gỡ bỏ hoàn toàn. Khi nhập /opt/bitnami, bncert-tool quét không thấy file nên báo lỗi.<br>- Tạo chứng chỉ SSL bằng certbot.<br>- Cấu hình tự động gia hạn chứng chỉ SSL cho certbot.<br>- Cấu hình tự động chuyển hướng HTTP sang HTTPS cho certbot.                                             | 29/09/2026   | 29/09/2026      | <https://000004.awsstudygroup.com/4-launchlinuxinstance/> |
| 4   | - Thiết lập Auto Snapshot (Tự động Backup) trên AWS Lightsail<br>- Chuyển Quản lý DNS của NameCheap sang AWS Route 53:<br>&emsp;+ Tạo Hosted Zone trên AWS Route 53<br>&emsp; + Copy 4 địa chỉ Name Server (NS) từ Route 53<br>&emsp;+ Tạo các bản ghi DNS trên Route 53<br>&emsp; + Cập nhật Name Server (NS) trên Namecheap<br>&emsp;+ Kiểm tra xem DNS đã chuyển sang Route 53 thành công chưa bằng dnschecker.org| 30/09/2026   | 30/09/2026      | <https://000010.awsstudygroup.com/1-introduce/> |
| 5   | - Tối ưu Lightsail Storage bằng AWS S3 & CloudFront:<br>&emsp;+ Tạo S3 Bucket.<br>&emsp;+ Tạo IAM Policy & User để cấp quyền cho WordPress.<br>&emsp;+ Tạo AWS CloudFront Distribution (CDN) đứng trước S3 để phân phối ảnh nhanh hơn.<br>&emsp;+ Cấu hình Plugin WP Offload Media trên WordPress để tự động đẩy media từ WordPress lên S3.<br>&emsp;                          | 1/10/2026 | 1/10/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Học và thực hành vẽ kiến trúc AWS trên draw.io                                                                                      | 2/10/2026 | 2/10/2026      | <https://youtu.be/l8isyDe-GwY?si=uqHosMXFWOeqSFcq> |


### Kết quả đạt được tuần 3:

* Tạo Lightsail instance với WordPress blueprint, gán static IP, đăng nhập WordPress Admin và dựng website thương mại điện tử bằng WooCommerce, theme Astra và Starter Templates.
* Mua tên miền trên Namecheap và trỏ DNS (A record) về static IP.
* Xử lý lỗi bncert-tool do Bitnami đã bỏ mô hình Monolithic, thay bằng certbot để cấp SSL, tự động gia hạn và chuyển hướng HTTP sang HTTPS.
* Thiết lập Auto Snapshot trên Lightsail và chuyển DNS từ Namecheap sang Route 53 (Hosted Zone, Name Server, bản ghi DNS), kiểm tra bằng dnschecker.org.
* Tạo S3 bucket, IAM policy/user và CloudFront distribution, cấu hình plugin WP Offload Media để tự động đẩy media lên S3.
* Học và thực hành vẽ sơ đồ kiến trúc AWS trên draw.io.
