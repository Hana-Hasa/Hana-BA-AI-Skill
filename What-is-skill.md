**Skill là gì?**

Trong ngữ cảnh này, "skill" (kỹ năng) là một công cụ hoặc quy trình được thiết kế để cấp cho AI (như Claude) khả năng thực hiện các tác vụ cụ thể, ví dụ như biến đổi tệp tin, trích xuất dữ liệu, tạo mã lập trình, hoặc tự động hóa một chuỗi các bước công việc.

**Cách tạo một skill chuẩn**Quá trình tạo ra và hoàn thiện một skill bao gồm các bước lặp đi lặp lại như sau:

**1. Xác định mục tiêu và thu thập thông tin (Capture Intent & Research)**

* Xác định rõ skill này sẽ giúp AI làm được gì, khi nào nó nên được kích hoạt (ngữ cảnh/câu lệnh của người dùng), và định dạng đầu ra mong đợi.
* Cần chủ động đặt câu hỏi về các trường hợp ngoại lệ (edge cases), các tệp ví dụ, tiêu chí thành công và các công cụ phụ thuộc đi kèm.

**2. Viết bản nháp cho skill (Write the SKILL.md)**

Một skill chuẩn được tổ chức theo cấu trúc 3 cấp độ:

* **Metadata (Tên & Mô tả):** Phần mô tả là cơ chế kích hoạt chính. Mô tả cần bao gồm cả chức năng và ngữ cảnh sử dụng**. Tài liệu khuyên phần mô tả nên có tính "thúc giục" (pushy) để tránh việc AI bỏ lỡ cơ hội sử dụng skill khi cần thiết**.
* **Phần thân SKILL.md:** Chứa các hướng dẫn cốt lõi, lý tưởng nhất là dưới 500 dòng**. Nên sử dụng câu mệnh lệnh và tập trung giải thích "lý do tại sao" một việc lại quan trọng thay vì chỉ đặt ra các quy tắc cứng nhắc (như BẮT BUỘC/KHÔNG BAO GIỜ)**.
* **Tài nguyên đi kèm:** Các script hỗ trợ, được tham chiếu rõ ràng từ phần thân**.**
* *Lưu ý:* Skill không được chứa mã độc hoặc các tính năng gây nguy hại đến bảo mật hệ thống**.**

**3. Xây dựng bài kiểm thử (Test Cases)**

Tạo từ 2 đến 3 câu lệnh (prompt) kiểm thử thực tế mô phỏng cách người dùng thực sự sẽ yêu cầu. Đối với các skill có đầu ra đánh giá được khách quan (như sinh mã, trích xuất dữ liệu), việc tạo bài test là rất cần thiết.

**4. Chạy thử nghiệm và Đánh giá (Run and Evaluate)**

* Chạy đồng thời hai hệ thống (subagents) cùng một lúc: một bên sử dụng skill và một bên cơ sở (baseline - không dùng skill hoặc dùng bản cũ) để so sánh.
* Tạo các tiêu chí đánh giá (assertions) khách quan có thể đo lường được.
* Chấm điểm kết quả, tổng hợp thống kê về tỷ lệ đạt, thời gian xử lý, lượng token sử dụng, và hiển thị trên một giao diện (viewer) để xem xét.

**5. Nhận phản hồi và Cải tiến (Improvement Loop)**

* Dựa vào phản hồi của người dùng hoặc điểm số để khái quát hóa các vấn đề.
* Loại bỏ các hướng dẫn rườm rà không mang lại hiệu quả trong prompt.
* Nếu nhận thấy AI thường xuyên phải lặp lại một khối lượng công việc giống nhau ở nhiều bài test khác nhau, hãy viết một script hỗ trợ chung (ví dụ: `build_chart.py`) và gắn nó vào thư mục tài nguyên của skill.
* Lặp lại quy trình kiểm thử và cải tiến này cho đến khi kết quả đầu ra làm hài lòng người dùng.

**6. Tối ưu hóa mô tả kích hoạt (Description Optimization)**

AI chỉ gọi skill khi nó đánh giá rằng yêu cầu của người dùng quá phức tạp để có thể tự xử lý. Do đó, bước này tạo ra khoảng 20 câu truy vấn đánh giá (bao gồm các câu "nên kích hoạt" và những câu bẫy "không nên kích hoạt") để huấn luyện và tối ưu hóa phần mô tả, giúp AI nhận diện và gọi skill chính xác nhất.

**7. Đóng gói (Package and Present)**

Sau khi hoàn thiện, skill sẽ được đóng gói thành tệp định dạng `.skill` để cung cấp cho người dùng cài đặt và sử dụng
