---
title: "Blog 1"
date: 2026-11-02
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AMAZON BEDROCK AGENTCORE: HẠ TẦNG CÒN THIẾU ĐỂ ĐƯA AI AGENT VÀO PRODUCTION

Làm một AI agent chạy được trên laptop thì không khó: một framework như LangGraph hay Strands Agents, một model và vài chục dòng code. Khó là bước sau đó: chạy cho hàng nghìn người dùng mà vẫn an toàn, theo dõi được và kiểm soát được. Đó chính là bài toán Amazon Bedrock AgentCore nhắm tới.

## AgentCore là gì?

AgentCore là nền tảng của AWS để xây dựng, triển khai và vận hành agent ở quy mô lớn. Nó gồm nhiều dịch vụ dạng module: dùng chung hoặc chỉ chọn phần bạn cần.

Điểm hay là nó không khóa framework hay model. AgentCore chạy được với CrewAI, LangGraph, LlamaIndex, Google ADK, OpenAI Agents SDK, Strands Agents và cả model ngoài Amazon Bedrock. Bạn giữ nguyên code agent, phần hạ tầng xung quanh để AgentCore lo.

## Các thành phần chính

| Dịch vụ | Vai trò |
|---|---|
| **Runtime** | Môi trường serverless để chạy agent và tool. Mỗi phiên người dùng được cô lập, tính phí theo CPU/RAM thực sự dùng. |
| **Memory** | Trí nhớ ngắn hạn (trong một cuộc hội thoại) và dài hạn (giữa các phiên), không phải tự dựng lớp lưu trữ. |
| **Gateway** | Biến API, Lambda và các dịch vụ khác thành tool cho agent gọi. Hỗ trợ MCP. |
| **Identity** | Cho agent đăng nhập vào hệ thống ngoài (Slack, Salesforce, API nội bộ) thay mặt người dùng. Tích hợp Cognito, Entra ID, Okta. |
| **Code Interpreter / Browser** | Chạy code trong sandbox và thao tác với trang web. |
| **Observability, Evaluations, Policy** | Trace trên CloudWatch, đánh giá chất lượng và đặt luật cho hành động của agent. |

## Phần mình thích nhất: Policy

Agent khác chatbot ở chỗ nó *hành động*: gọi API, hoàn tiền, sửa dữ liệu. Chỉ dặn model "cẩn thận nhé" trong prompt thì rất mong manh.

Policy đưa việc kiểm soát ra khỏi agent. Luật viết bằng Cedar và được áp ở Gateway. Khi Policy Engine bật chế độ ENFORCE, mọi lần gọi tool đều bị kiểm tra trước khi chạy, nên độ an toàn không còn phụ thuộc vào việc model có "ngoan" hay không.

## Khi nào nên dùng?

Hợp khi bạn đã có prototype chạy tốt và cần cô lập phiên, kiểm soát quyền, giám sát. Với demo nhỏ hay project học tập, một cách dựng đơn giản có thể là đủ, vì AgentCore sinh ra cho quy mô production. Các dịch vụ đều hỗ trợ kết nối VPC, tiện khi dữ liệu cần giữ trong mạng riêng.

## Thực hành: deploy agent đầu tiên

Phần này làm theo bản quickstart chính thức dùng AgentCore CLI.

**Chuẩn bị:** tài khoản AWS đã cấu hình credentials, Node.js 20.12+, Python 3.10+ và [uv](https://docs.astral.sh/uv/getting-started/installation/).

**1. Cài CLI**

```bash
npm install -g @aws/agentcore
agentcore --version
```

Nếu báo lỗi, có thể lệnh `agentcore` bản Python cũ đang chặn. Chạy `pip uninstall bedrock-agentcore-starter-toolkit` rồi mở terminal mới.

**2. Tạo project** (agent Python dùng Strands Agents + Amazon Bedrock, kèm sẵn AgentCore Memory)

```bash
agentcore create --name MyProject --template agent-python-strands
cd MyProject
```

**3. Chạy thử ở máy.** Lệnh này mở trình duyệt để chat với agent và xem trace.

```bash
agentcore dev --mode browser
```

**4. Deploy.** Lần đầu mất vài phút vì CDK phải bootstrap tài khoản.

```bash
agentcore build
agentcore deploy
agentcore status
```

**5. Gọi agent đã deploy**

```bash
agentcore invoke --runtime agent --payload '{"prompt":"Hello, what can you do?"}'
```

**6. Xem log và trace**

```bash
agentcore logs runtime --since 30m
agentcore traces runtime list --since 30m
```

**7. Dọn tài nguyên** để tránh phát sinh chi phí

```bash
agentcore remove all --yes
agentcore deploy --yes
```

Sau đó bạn có thể thêm `agentcore add memory`, `agentcore add gateway`, `agentcore add runtime` rồi `agentcore deploy` lại để gắn thêm tính năng.

## Điều rút ra

* Nút thắt của AI agent không còn là model, mà là hạ tầng xung quanh: bộ nhớ, quyền truy cập, giám sát, kiểm soát.
* Dịch vụ dạng module, không khóa framework giúp đưa agent có sẵn lên production mà không phải viết lại.
* Nên kiểm soát hành động của agent ở tầng hạ tầng (Policy), không chỉ dựa vào prompt.

## Tài liệu tham khảo

* [What is Amazon Bedrock AgentCore? (AWS Docs)](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/what-is-bedrock-agentcore.html)
* [Amazon Bedrock AgentCore (AWS Prescriptive Guidance)](https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-frameworks/amazon-bedrock-agentcore.html)
* [Get started with Amazon Bedrock AgentCore (AWS Docs)](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/agentcore-get-started-cli.html)

![post on AWS Study Group VN Fb Group](/fcj-workshop-template/images/3-BlogsPosted/blog1.jpg)
