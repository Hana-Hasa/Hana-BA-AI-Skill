# Skill: Competitive Research

> Nghiên cứu thị trường và đối thủ cạnh tranh để hỗ trợ quyết định chiến lược sản phẩm.

---

## Khi nào dùng skill này

- BA / PM cần hiểu đối thủ đang làm gì trước khi define feature mới
- Cần benchmark sản phẩm với thị trường (pricing, feature set, UX)
- Muốn tìm khoảng trống thị trường (market gap) để đề xuất hướng phát triển
- Chuẩn bị business case với dữ liệu thị trường thực tế

---

## Inputs

- Tên sản phẩm / tính năng cần research
- Danh sách đối thủ cần so sánh (nếu đã biết)
- Câu hỏi cụ thể cần trả lời (optional)

---

## Output Format

Một bảng so sánh competitive + tóm tắt điểm mạnh/yếu + recommendation.

**Template:**

```
## Competitive Research: [Tên tính năng / sản phẩm]
Ngày: [DD/MM/YYYY]

### 1. Tổng quan thị trường
[Mô tả ngắn bối cảnh thị trường]

### 2. So sánh đối thủ

| Tiêu chí       | [Sản phẩm mình] | [Đối thủ A] | [Đối thủ B] |
|---|---|---|---|
| [Tiêu chí 1]   |                 |             |             |
| [Tiêu chí 2]   |                 |             |             |
| Pricing        |                 |             |             |
| UX / Ease of use |               |             |             |

✅ Ký hiệu: ✅ Có | ❌ Không | ⚠️ Có nhưng giới hạn

### 3. Điểm mạnh của mình vs. thị trường
-

### 4. Khoảng trống thị trường (Opportunity)
-

### 5. Recommendation
-
```

---

## Bước thực hiện

### Bước 1 — Xác định scope research

Research không có scope thì dễ lan rộng và mất thời gian.

1. Xác định **câu hỏi cốt lõi** cần trả lời (VD: "Đối thủ có tính năng X chưa?")
2. Chọn tối đa 3–5 đối thủ trực tiếp để so sánh
3. Chọn 5–8 tiêu chí so sánh có liên quan nhất

### Bước 2 — Thu thập thông tin

Các nguồn nên tham khảo:
- Trang web / app của đối thủ
- App Store / Google Play reviews
- G2, Capterra, ProductHunt
- LinkedIn, blog công ty
- Báo cáo ngành (nếu có)

### Bước 3 — Điền bảng so sánh và phân tích

Điền từng tiêu chí theo thực tế, không phỏng đoán. Ghi rõ nguồn nếu cần.

### Bước 4 — Rút ra Recommendation

Từ bảng so sánh, trả lời:
- Mình đang **tốt hơn** đối thủ ở đâu?
- Mình đang **thua** ở đâu? Có cần làm gì không?
- Có **cơ hội** nào mà đối thủ chưa khai thác?

---

## Ví dụ

**Input:** "Research tính năng OTP / 2FA của các app fintech cạnh tranh với VNG Pay"

**Output:**
```
Competitive Research: 2FA / OTP trong Fintech Apps
Ngày: 10/03/2026

So sánh: MoMo | ZaloPay | ViettelMoney | VNG Pay

Tiêu chí         | VNG Pay | MoMo | ZaloPay | ViettelMoney
SMS OTP          | ✅      | ✅   | ✅      | ✅
Authenticator app| ❌      | ⚠️  | ✅      | ❌
Biometric login  | ✅      | ✅   | ✅      | ⚠️
Remember device  | ❌      | ✅   | ✅      | ❌

Opportunity: Thêm "Remember device" + Authenticator app
để giảm friction cho power users.
```

---

## Limitations

- ❌ Không tự crawl web — BA cần cung cấp thông tin hoặc paste nội dung vào
- ❌ Không verify pricing realtime — dữ liệu có thể lỗi thời
- ✅ Dùng tốt nhất khi BA đã có sẵn một số thông tin và cần tổng hợp / phân tích

## Related Skills

- `strategy-analysis/business-case-generator.md` — dùng kết quả research này để build business case
- `strategy-analysis/swot-canvas-builder.md` — input competitive research vào SWOT
