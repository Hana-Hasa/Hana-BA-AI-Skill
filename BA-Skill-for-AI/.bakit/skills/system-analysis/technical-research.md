# Skill: Technical Research

> Nghiên cứu và đánh giá các lựa chọn kỹ thuật từ góc nhìn BA — không cần biết code, vẫn hiểu đủ để làm việc với Dev/Architect.

---

## Khi nào dùng skill này

- Cần hiểu một công nghệ / API / platform để viết requirement chính xác hơn
- Muốn so sánh các giải pháp kỹ thuật từ góc độ business impact
- Cần evaluate vendor / third-party solution (ví dụ: chọn payment gateway, SMS provider)
- Chuẩn bị câu hỏi kỹ thuật trước khi làm việc với Dev team

---

## Inputs

- Tên công nghệ / giải pháp / vendor cần research
- Câu hỏi cụ thể cần trả lời (VD: "Giải pháp A có hỗ trợ webhook không?")
- Constraints đã biết (budget, timeline, existing tech stack — nếu có)

---

## Output Format

**Template:**

```
## Technical Research: [Tên chủ đề]
Ngày: [DD/MM/YYYY]
Người thực hiện: [Tên BA]

### 1. Bối cảnh & Câu hỏi cần trả lời
[Tại sao cần research cái này?]
Câu hỏi:
- [Q1]
- [Q2]

### 2. Các lựa chọn đang xem xét
| Tiêu chí              | Lựa chọn A | Lựa chọn B | Lựa chọn C |
|---|---|---|---|
| Tính năng phù hợp     | ✅ / ❌    |            |            |
| Độ phức tạp tích hợp  | Thấp/TB/Cao|            |            |
| Chi phí (ước tính)    |            |            |            |
| Vendor support        |            |            |            |
| Rủi ro chính          |            |            |            |

### 3. Phân tích Business Impact
[Mỗi lựa chọn ảnh hưởng đến user / business như thế nào?]

### 4. Recommendation
Đề xuất: [Lựa chọn X] vì [lý do business rõ ràng]

Điều kiện để áp dụng:
- [Điều kiện 1]
- [Điều kiện 2]

### 5. Câu hỏi cần confirm với Dev / Architect
- [Q1 — cần xác nhận về kỹ thuật]
- [Q2]
```

---

## Bước thực hiện

### Bước 1 — Đặt câu hỏi research rõ ràng

Research kỹ thuật dễ bị "rabbit hole". Bắt đầu bằng câu hỏi cụ thể:

```
❌ "Research về OAuth"
✅ "OAuth 2.0 có phù hợp để implement SSO cho hệ thống internal tool không?
    Team có ~50 users, muốn dùng Google account."
```

### Bước 2 — Liệt kê các lựa chọn

- Nhờ AI gợi ý 2–4 lựa chọn phổ biến cho use case đó
- Không cần đi sâu vào code — tập trung vào: capability, integration effort, cost, risk

### Bước 3 — So sánh từ góc nhìn business

Với mỗi lựa chọn, hỏi:
- Nó giải quyết được vấn đề của user không?
- Dev mất bao lâu để tích hợp? (ảnh hưởng timeline)
- Có vendor lock-in không? (ảnh hưởng chiến lược dài hạn)
- Chi phí vận hành như thế nào?

> 💡 BA không cần hiểu technical implementation — chỉ cần hiểu **trade-off** để trình bày với stakeholder.

### Bước 4 — Chuẩn bị câu hỏi cho Dev

Sau khi có hình dung, liệt kê những gì cần Dev xác nhận:
- Tính khả thi kỹ thuật với hệ thống hiện tại
- Effort estimate
- Security / compliance concerns

---

## Ví dụ

**Input:** "Cần chọn giải pháp gửi email notification cho hệ thống. Hiện tại dùng SMTP nội bộ, đang xem xét chuyển sang SendGrid hoặc AWS SES."

**Output (tóm tắt):**
```
Tiêu chí          | SMTP nội bộ | SendGrid   | AWS SES
Deliverability    | ⚠️ Thấp    | ✅ Cao     | ✅ Cao
Chi phí           | Thấp (fixed)| ~$20/100k | ~$0.10/1k
Tích hợp dev      | ✅ Đã có   | Dễ (API)   | TB (cần config)
Analytics         | ❌          | ✅ Dashboard| ⚠️ Basic
Rủi ro spam       | ⚠️ Cao     | Thấp       | Thấp

Recommendation: AWS SES nếu đã dùng AWS stack,
SendGrid nếu cần dashboard analytics cho Marketing team.

Câu hỏi cho Dev:
- Hệ thống có đang chạy trên AWS không?
- Marketing team có cần xem email analytics không?
```

---

## Limitations

- ❌ Không thể kiểm tra code hoặc chạy thử giải pháp kỹ thuật
- ❌ Thông tin về pricing / feature của vendor có thể thay đổi — cần verify lại
- ✅ Dùng tốt nhất để chuẩn bị conversation với Dev, không thay thế technical design

## Related Skills

- `strategy-analysis/competitive-research.md` — nếu cần so sánh vendor ở góc độ thị trường
- `system-analysis/impact-analysis.md` — sau khi chọn được giải pháp, phân tích impact
- `system-analysis/risk-analysis.md` — đánh giá rủi ro của lựa chọn kỹ thuật
