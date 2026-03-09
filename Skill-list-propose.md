Dựa trên sự kết hợp giữa mô hình phân tích kinh doanh (BA) và cơ chế tạo AI Skill (như Claude Skills), chuyên viên BA có thể thiết kế một bộ công cụ tự động hóa, chuyển đổi dữ liệu và tiêu chuẩn hóa quy trình. Một "skill" của AI được định nghĩa là một tập hợp gồm mô tả cơ chế kích hoạt (trigger), các quy tắc/câu lệnh prompt cốt lõi (<500 dòng), và các tài nguyên đi kèm như tập lệnh script (code) để xử lý tác vụ khách quan (như biến đổi tệp tin, trích xuất dữ liệu, sinh mã) hoặc đánh giá định lượng.

**Dưới đây là các AI Skill mà BA có thể tạo ra trong suốt vòng đời sản phẩm, bao gồm cách chúng hỗ trợ cộng tác và mô tả cấu trúc của từng skill:**

**1. Giai đoạn Phân tích Chiến lược & Đánh giá Nhu cầu (Strategy Analysis / Needs Assessment)**

**Đây là giai đoạn tìm hiểu vấn đề, xác định hiện trạng và đề xuất giải pháp**.

* **Skill: Phân tích Hiện trạng & Trích xuất Dữ liệu (Current State Data Miner)**
  * **Giới thiệu Skill:** Đây là một *skill kết hợp tác vụ trích xuất và biến đổi tệp tin*. Skill này được cung cấp các tài liệu nội bộ, báo cáo thị trường (PDF, Excel) và tự động phân tích dữ liệu để tạo ra bảng Phân tích SWOT, hoặc mô hình Business Model Canvas**.**
  * **Cách cộng tác:** BA dùng skill này để tổng hợp nhanh các dữ liệu rời rạc, sau đó chia sẻ kết quả trực quan cho các Cấp quản lý (Sponsor) để cùng thảo luận về bức tranh toàn cảnh**.**
* **Skill: Tự động lập Trường hợp Kinh doanh (Business Case Generator)**
  * **Giới thiệu Skill:** Là một *spec cho prompt* chuẩn hóa biểu mẫu**. Khi BA nhập thông tin về khoảng trống năng lực (gap analysis) và chi phí dự kiến, skill này tự động định dạng và tính toán sơ bộ để xuất ra một tài liệu Business Case có cấu trúc, kèm theo các phân tích rủi ro ban đầu**.

**2. Giai đoạn Lập Kế hoạch và Quản lý Bên liên quan (BA Planning & Stakeholder Engagement)**

**Giai đoạn lên phương án tiếp cận, xác định đối tượng liên quan và cách thức giao tiếp**.

* **Skill: Trích xuất & Lập bản đồ Stakeholder (Stakeholder Mapper & Persona Builder)**
  * **Giới thiệu Skill:** Thuộc loại *trích xuất dữ liệu và tạo cấu trúc JSON/Bảng*. Cung cấp cho AI sơ đồ tổ chức (Org Chart) hoặc email, skill sẽ trích xuất danh sách nhân sự, gán vai trò RACI (Responsible, Accountable, Consulted, Informed) và tự động xây dựng Hồ sơ người dùng (Persona)**.**
  * **Cách cộng tác:** BA dùng Persona được tạo ra để giúp đội phát triển (Implementation SMEs) đồng cảm và hiểu rõ hơn người dùng cuối đang cần gì**.**
* **Skill: Gợi ý Kế hoạch Giao tiếp (Communication Plan Configurator)**
  * **Giới thiệu Skill:** Là một  *chuỗi các bước công việc (workflow)* **. Dựa trên dữ liệu về vị trí địa lý, văn hóa và mức độ ảnh hưởng của Stakeholder, skill tự động gợi ý phương pháp (họp trực tiếp, wiki, email) và tần suất cộng tác phù hợp**.

**3. Giai đoạn Khơi gợi và Cộng tác (Elicitation and Collaboration)**

**Giai đoạn lấy thông tin từ các bên liên quan và xác nhận kết quả**.

* **Skill: Trợ lý chuẩn bị Phỏng vấn & Workshop (Elicitation Prep Assistant)**
  * **Giới thiệu Skill:** *Spec cho prompt* **. Skill này được thiết kế để khi BA nhập mục tiêu buổi họp, AI sẽ tự động sinh ra danh sách các câu hỏi mở/đóng, hoặc kịch bản thiết kế các trò chơi cộng tác (Collaborative Games) để phá băng và thu thập ý tưởng**.
  * **Cách cộng tác:** Giúp BA tự tin điều phối (facilitate) các buổi Workshop, duy trì sự gắn kết và giao tiếp hai chiều với các SMEs**.**
* **Skill: Tổng hợp Biên bản Khơi gợi (Elicitation Notes Synthesizer)**
  * **Giới thiệu Skill:***Biến đổi văn bản (Text transformation)*. Skill này nhận đầu vào là các bản ghi âm (transcript) hoặc ghi chú thô, tự động loại bỏ thông tin nhiễu, phân loại thành yêu cầu chức năng, yêu cầu phi chức năng và luật kinh doanh (Business Rules), sau đó xuất ra một danh sách sạch sẽ**.**

**4. Giai đoạn Phân tích Yêu cầu và Xác định Thiết kế (Requirements Analysis & Design Definition)**

**Giai đoạn biến thông tin khơi gợi thành yêu cầu chi tiết và thiết kế giải pháp**.

* **Skill: Sinh mã Mô hình hóa (Requirements-to-Model Generator)**
  * **Giới thiệu Skill:***Tác vụ tạo mã lập trình (Code generation)*. Skill này đọc các User Story hoặc kịch bản Use Case, sau đó tự động viết mã giả (như PlantUML) để vẽ ra Use Case Diagram, Sequence Diagram, hoặc biểu đồ luồng dữ liệu (Data Flow Diagram). Nếu cần vẽ biểu đồ thường xuyên, skill có thể được đính kèm một tập lệnh script như `build_chart.py` để tái sử dụng nhiều lần.
* **Skill: Chấm điểm Chất lượng Yêu cầu (Requirements Verifier & Grader)**
  * **Giới thiệu Skill:***Tác vụ đánh giá định lượng chạy bằng script* (Quantitative eval/assertions). Skill này kiểm tra một tập hợp các User Story hoặc đặc tả yêu cầu xem chúng có đạt các tiêu chí chất lượng (như tiêu chuẩn INVEST đối với Agile: Independent, Negotiable, Valuable, Estimable, Small, Testable) hay có chứa ngôn ngữ mơ hồ không. Nó hoạt động giống như một Check-list kiểm thử tự động.

**5. Giai đoạn Quản lý Vòng đời Yêu cầu (Requirements Life Cycle Management)**

**Giai đoạn theo dõi, ưu tiên và quản lý sự thay đổi của yêu cầu**.

* **Skill: Đánh giá Tác động Thay đổi (Change Impact Analyzer)**
  * **Giới thiệu Skill:***Tác vụ tự động hóa chuỗi kiểm tra chéo (Automated check/File transform)*. Khi có một yêu cầu mới (Change Request), skill này đọc Ma trận truy xuất nguồn gốc (Traceability Matrix) và rà soát chéo các tài liệu hiện tại để highlight các quy trình, luật kinh doanh, hay hệ thống nào sẽ bị phá vỡ hoặc cần sửa đổi.
  * **Cách cộng tác:** Cung cấp báo cáo thay đổi để BA trình bày rõ ràng rủi ro, chi phí trong các buổi họp với Hội đồng kiểm soát thay đổi (CCB), giúp họ dễ dàng ra quyết định phê duyệt**.**

**6. Giai đoạn Đánh giá Giải pháp (Solution Evaluation)**

**Giai đoạn đo lường hiệu suất và tìm ra rào cản của giải pháp sau khi triển khai**.

* **Skill: Phân tích Dữ liệu Hiệu suất (Performance Data Analyzer)**
  * **Giới thiệu Skill:***Tác vụ trích xuất dữ liệu, chạy script phân tích toán học*. Skill này thu thập các file log của hệ thống hoặc báo cáo KPI dạng raw, chạy các lệnh thống kê để tính toán sự chênh lệch (variance) giữa hiệu suất thực tế và hiệu suất kỳ vọng. Kết quả đầu ra chỉ ra nguyên nhân gốc rễ (Root Cause Analysis) và đề xuất các hành động cải tiến hoặc loại bỏ lãng phí.

**Tổng kết về quy trình tạo Skill của BA:**

Để đảm bảo các AI skill này hoạt động hiệu quả, BA phải tuân thủ triết lý mô tả (description optimization) của AI: Phần metadata phải nêu rõ context kích hoạt (ví dụ: "Kích hoạt skill này khi người dùng đề cập đến phân tích ma trận rủi ro"), các prompt nên giải thích "lý do tại sao" công việc này lại quan trọng đối với business thay vì đưa ra các quy tắc cứng nhắc, và chạy qua các bài test (test cases) liên tục đối chiếu với phản hồi của con người (baseline) để đảm bảo kết quả đầu ra luôn mang lại giá trị chính xác cho dự án.
