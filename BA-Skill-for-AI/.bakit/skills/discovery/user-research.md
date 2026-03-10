# Skill: User Research

> Tổng hợp và phân tích dữ liệu từ user interview, survey, hoặc usability test để hiểu nhu cầu thực sự của người dùng.

---

## Khi nào dùng skill này

- Sau khi thực hiện user interview / survey cần tổng hợp insight
- Muốn tìm pain point thực tế của user từ dữ liệu thô
- Cần validate ý tưởng tính năng với feedback người dùng
- Chuẩn bị input cho persona creation hoặc user story writing

---

## Inputs

Cung cấp ít nhất một trong các nguồn sau:
- Biên bản / transcript phỏng vấn người dùng
- Kết quả survey (raw data hoặc tổng hợp)
- Log hỗ trợ / ticket CS có liên quan
- Usability test feedback

---

## Output Format

Báo cáo insight ngắn gọn theo theme + danh sách pain point + quote nổi bật.

**Template:**

```
## User Research Summary: [Chủ đề / Tính năng]
Nguồn: [Interview n=X | Survey n=X | CS tickets]
Ngày: [DD/MM/YYYY]

### Key Insights (theo theme)

**Theme 1: [Tên theme]**
- Insight: [mô tả]
- Dẫn chứng: "[quote từ user]"
- Tần suất: X/Y người đề cập

**Theme 2: [Tên theme]**
...

### Top Pain Points
1. [Pain point quan trọng nhất]
2. [Pain point tiếp theo]
3. ...

### Opportunity / Implication cho Product
- [Insight → Hướng giải quyết]

### Quotes nổi bật
> "[Quote user 1]" — [vai trò / segment]
> "[Quote user 2]" — [vai trò / segment]
```

---

## Bước thực hiện

### Bước 1 — Đọc và gắn tag cho dữ liệu thô

Đây là bước quan trọng nhất — đọc kỹ trước khi phân tích.

1. Paste dữ liệu thô vào (transcript, survey responses)
2. Yêu cầu AI gắn tag theo theme: pain point / positive / suggestion / question
3. Xác nhận các tag có hợp lý không

### Bước 2 — Cluster insights theo theme

Gom các feedback tương đồng thành nhóm (affinity mapping).

```
💡 Mỗi theme nên có tên rõ ràng, VD:
   "Khó tìm lại lịch sử giao dịch"
   "Không hiểu tại sao bị từ chối thanh toán"
```

### Bước 3 — Xếp hạng Pain Points

Ưu tiên theo:
- **Tần suất**: bao nhiêu người đề cập?
- **Mức độ ảnh hưởng**: block workflow hay chỉ annoying?
- **Sentiment**: user có frustrated không?

### Bước 4 — Rút ra implication cho Product

Mỗi pain point → một opportunity statement:
```
"Vì users gặp khó khăn với X, nên chúng ta nên cân nhắc Y"
```

---

## Ví dụ

**Input:** Transcript 5 buổi phỏng vấn user về quy trình đăng ký tài khoản VKS

**Output (tóm tắt):**
```
Top Pain Points:
1. Không biết đang ở bước nào trong quy trình (4/5 users)
2. Form yêu cầu thông tin không rõ ràng — "trường này nhập gì?" (3/5)
3. Không có thông báo khi bị từ chối (5/5 — critical)

Opportunity:
→ Thêm progress bar + tooltip giải thích từng field
→ Thiết kế rejection email rõ lý do + hướng dẫn fix
```

---

## Limitations

- ❌ Không tự thu thập dữ liệu — BA cần cung cấp raw data
- ❌ Kết quả bị giới hạn bởi chất lượng và số lượng nguồn input
- ✅ Dùng tốt nhất với 5+ interview hoặc 20+ survey responses

## Related Skills

- `stakeholder-planning/persona-creation.md` — dùng insights để build persona
- `discovery/problem-analysis.md` — đào sâu vào pain point cụ thể
- `requirement/userstory-writing.md` — chuyển insights thành user story
