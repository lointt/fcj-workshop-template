---
title: "Event 2"
date: 2026-09-29
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch “AWS Cloud and AI Day Hanoi”

### Mục Đích Của Sự Kiện

- Chia sẻ cách doanh nghiệp áp dụng agentic AI mà vẫn kiểm soát được chi phí, dữ liệu và quy trình
- Giới thiệu Amazon Quick và Kiro như một nền tảng AI thống nhất cho khối business và engineering
- Giới thiệu AWS Security Agent giúp bảo mật ứng dụng chủ động từ thiết kế đến triển khai
- Giới thiệu MCP và các AWS MCP servers để kết nối AI agent với dịch vụ AWS

### Danh Sách Diễn Giả

- **Tuan Vo** - Sr. Solutions Architect, G-AsiaPacific Vietnam (Session PRT201-S, Level 200)
- **Trung Nguyen** - Technical Account Manager, AWS Vietnam (Session DVT305, Level 300)
- **Tan Huynh** - Technical Account Manager, AWS Vietnam (Session DVT305, Level 300)

### Nội Dung Nổi Bật

#### Session 1: Adopt Agentic AI Without Losing Control

**Thực trạng áp dụng AI trong doanh nghiệp**

Nhân viên dùng AI mỗi ngày, nhưng ban lãnh đạo thường không biết họ dùng công cụ nào, dùng như thế nào, hay dữ liệu đi đâu.

- **Business users**: khó khai thác dữ liệu nội bộ (CRM, hồ sơ khách hàng), tự động hóa kém (vẫn copy-paste thủ công), rủi ro quản trị dữ liệu, không có audit trail
- **IT / Engineering**: không kiểm soát được chi phí (không thấy token dùng vào đâu), không kiểm soát việc dùng ngoài mục đích (license dùng cho việc cá nhân), không đo được ROI, quy trình chưa chuẩn hóa
- **Kết luận**: AI đang được dùng nhưng chưa được quản trị. Doanh nghiệp cần một nền tảng AI thống nhất để kiểm soát chi phí và dữ liệu, đồng thời tăng năng suất.

**Monitor — Control — Standardize**

Thông điệp cốt lõi của session, áp dụng cho cả business users và kỹ sư.

**Amazon Quick – Nền tảng AI Agent thống nhất**

- Một nền tảng thay thế nhiều công cụ rời rạc; có trên desktop, web và mobile
- **Enterprise intelligence**: hỗ trợ nguồn dữ liệu on-premises, cloud và SaaS
- **Automation**: lập kế hoạch và thực thi workflow phức tạp
- **Security & governance**: access control, guardrails, dashboard, audit
- **Mở rộng Quick** (từ no-code đến high-code): Custom Chat Agent, Quick Sight (BI và trực quan hóa dữ liệu), Research (phân tích chuyên sâu, xuất báo cáo), Amazon Bedrock AgentCore (xây dựng multi-agent tùy chỉnh với bảo mật và governance)

**Kiro – IDE thế hệ mới cho Engineering**

- Có dạng IDE, CLI và ACP, bao phủ Docs → Build → Package → Deploy → Operate
- **Auto-select**: Kiro tự chọn model tối ưu theo độ phức tạp của task, giúp tối ưu chi phí
- Các model gồm Claude Opus 5 (suy luận phức tạp, kiến trúc), GPT 5.6 (đa dụng, context dài), Deepseek v3.2 (sinh code, tiết kiệm), Minimax M2.5 (đa ngôn ngữ, suy luận nhanh), GLM 5 (khả năng reasoning), Qwen3 Coder (tối ưu cho code, chi phí thấp), cùng 12 model khác

**Governance & Process Standardization**

- **Governance**: usage dashboard, prompt logs, budget cap và alerts
- **Process**: AI-DLC, spec-driven development, property-based testing
- Mục tiêu: chuyển từ “dùng AI” sang “quản trị AI” trong phát triển phần mềm

**Lộ trình 3 giai đoạn (Your Path Forward)**

- **Phase 1 – Assess (2–4 tuần)**: kiểm kê các công cụ AI đang dùng, tìm điểm thất thoát chi phí, phân mảnh và lỗ hổng governance, chạy thử Quick và Kiro với một team trên use case thực tế
- **Phase 2 – Migrate (1–3 tháng)**: triển khai Quick cho toàn bộ business team, đưa kỹ sư vào dùng Kiro xuyên suốt SDLC, tập trung hóa dashboard, ngân sách và audit logs
- **Phase 3 – Extend (liên tục)**: chuẩn hóa bằng spec-driven dev, hooks và AI-DLC, phân tích mức sử dụng để tối ưu chi phí, xây agent tùy chỉnh trên Bedrock AgentCore
- Phương châm: *Govern first — Migrate smart — Scale with confidence.*

#### Session 2: AWS Security Agent – Proactive AppSec from Design to Deployment

**Bảo mật chủ động xuyên suốt vòng đời phát triển**

- **Design review (vài phút)**: đánh giá tài liệu thiết kế theo các yêu cầu bảo mật chuẩn
- **Threat model (vài phút)**: phân tích kiến trúc ứng dụng và xác định các mối đe dọa
- **Code review (gần thời gian thực)**: phân tích bảo mật mã nguồn trên pull request, diff và toàn bộ repository
- **Penetration testing (vài giờ)**: phát hiện và liên kết các lỗ hổng đã được xác thực qua các kịch bản tấn công nhiều bước
- Hoạt động ở bất kỳ đâu ứng dụng được xây dựng và chạy: AWS, multicloud, SaaS và hybrid / on-premises

**AWS Security Agent là gì?** Pentest tự động có nhận biết ngữ cảnh (context-aware autonomous penetration testing).

- **AI-powered pentesting**: kết hợp SAST, DAST, SCA và pentest tự động trong một giải pháp
- **Context awareness**: tiếp nhận design docs, API, IaC, threat model, user stories và endpoints để tùy biến kịch bản tấn công
- **Validated security risks**: liên kết các lỗ hổng thành chuỗi tấn công có thể chứng minh và tái hiện, giảm false positive và alert fatigue

**Tóm tắt tính năng**

- Threat model dựa trên STRIDE, tự động tạo từ codebase và tài liệu thiết kế
- Dịch vụ được AWS quản lý hoàn toàn, không cần dựng hạ tầng
- Tích hợp repository: GitHub, GitLab, Bitbucket và upload lên Amazon S3
- Hỗ trợ 9 regions
- **Giá**: pay-as-you-go, $50 mỗi agent-hour cho penetration testing, tính theo từng giây, không trả trước và không cam kết tối thiểu
- **Dùng thử miễn phí**: 2 tháng, 400 task-hours mỗi tháng (nằm trong AWS Free Tier)

**MCP và AWS MCP servers**

- Agenda: giới thiệu nhanh về MCP và AWS MCP servers, Agent Toolkit for AWS, nâng cấp với knowledge servers của riêng bạn, Q&A
- AWS MCP servers: hơn 9.700 stars trên GitHub, 60+ servers, 300+ dịch vụ AWS, 20+ bài viết từ cộng đồng

### Những Gì Học Được

#### Tư Duy Quản Trị

- Áp dụng AI mà không có khả năng quan sát sẽ gây rủi ro về chi phí, dữ liệu và tuân thủ
- **Monitor — Control — Standardize** là nguyên tắc dẫn đường
- Nên bắt đầu bằng đánh giá hiện trạng và pilot nhỏ trước khi triển khai toàn tổ chức

#### Kiến Trúc Kỹ Thuật

- Một nền tảng thống nhất (Quick cho business, Kiro cho engineering) tốt hơn nhiều công cụ rời rạc
- Tự động chọn model theo độ phức tạp của task giúp cân bằng chất lượng và chi phí
- Bảo mật nên được áp dụng ở mọi giai đoạn: thiết kế, threat modeling, code và testing
- MCP servers giúp AI agent làm việc với các dịch vụ AWS theo cách chuẩn hóa

#### Chiến Lược Hiện Đại Hóa

- **Lộ trình theo giai đoạn**: Assess → Migrate → Extend
- Đo lường ROI bằng usage dashboard, prompt logs và budget cap
- Chuẩn hóa phát triển bằng spec-driven development, AI-DLC và property-based testing

### Ứng Dụng Vào Công Việc

- **Kiểm kê công cụ AI** đang dùng trong team và project, ghi nhận rủi ro về chi phí và dữ liệu
- **Thử Kiro** với spec-driven development trong bài tập và project nhóm
- **Áp dụng ý tưởng của Security Agent** (design review, threat modeling, code review) trước khi triển khai project
- **Thử nghiệm AWS MCP servers** để kết nối trợ lý AI với tài nguyên AWS
- **Đặt giới hạn ngân sách và theo dõi mức sử dụng** khi dùng dịch vụ AI hoặc cloud

### Trải nghiệm trong event

Tham gia **AWS Cloud and AI Day Hanoi** giúp tôi có cái nhìn thực tế về cách AI được áp dụng và bảo mật trong các tổ chức.

#### Học hỏi từ các diễn giả có chuyên môn cao
- Các diễn giả từ G-AsiaPacific và AWS Vietnam chia sẻ những vấn đề thực tế khi doanh nghiệp áp dụng AI và cách giải quyết cụ thể.
- Lộ trình và ví dụ về giá giúp các ý tưởng dễ áp dụng hơn.

#### Trải nghiệm công cụ thực tế
- Thấy được Amazon Quick, Kiro và AWS Security Agent nằm ở đâu trong quy trình business, phát triển và bảo mật.
- Hiểu rằng governance (dashboard, logs, ngân sách) quan trọng không kém bản thân model AI.

#### Kết nối và trao đổi
- Các câu hỏi trong session và trao đổi với những người tham dự khác cho thấy nhiều team cùng gặp mối lo về chi phí, dữ liệu và bảo mật.

#### Bài học rút ra
- Cần kiểm soát và chuẩn hóa trước khi mở rộng AI.
- Bảo mật hiệu quả nhất khi bắt đầu từ lúc thiết kế, không phải sau khi triển khai.
- Chọn đúng model và công cụ cho từng task giúp tiết kiệm cả chi phí lẫn công sức.

#### Một số hình ảnh khi tham gia sự kiện
![image event2](/fcj-workshop-template/images/4-EventParticipated/event2.jpg)

> Tổng thể, sự kiện giúp tôi nhìn AI không chỉ là công cụ tăng năng suất mà còn là một hệ thống cần được giám sát, bảo mật và quản trị.
