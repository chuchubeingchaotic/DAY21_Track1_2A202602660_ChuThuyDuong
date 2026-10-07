# Nhật ký hỗ trợ AI — Day 21

- Học viên: Chu Thùy Dương
- Mã học viên: 2A202602660
- Lớp: Track 1
- Dự án: P-092 — Clear Hire, hệ thống sàng lọc CV kết hợp Human-in-the-Loop
- Công cụ AI hỗ trợ: Antigravity
- Thời gian thực hiện: 07/10/2026

---

## 1. Mục đích sử dụng AI
Em sử dụng AI như một trợ lý nghiên cứu và phản biện chuyên sâu để:
- Tra cứu, tổng hợp các án lệ và sự cố thực tế kinh điển về an toàn AI (Responsible AI / AI Safety & Bias) trong lĩnh vực HR Tech và sàng lọc ứng viên.
- Xác thực số liệu, mốc thời gian và nguồn trích dẫn pháp lý chính thống của 3 case nghiên cứu (Amazon AI recruiting tool, HireVue facial analysis, iTutorGroup age discrimination lawsuit).
- Xây dựng ma trận Bản đồ Tác hại (Harm Map Worksheet) phân bổ đa tầng (Model, Grounding, Safety, UX) theo chuẩn mực AI Governance.
- Phản biện và đối chiếu các giải pháp phòng ngừa rủi ro để đưa vào thiết kế kiến trúc thực tế của dự án cá nhân P-092 (Clear Hire).

---

## 2. Quá trình làm việc chi tiết

### Giai đoạn 1: Xác định phạm vi và chuẩn hóa thuật ngữ
- **Nội dung**: Đọc kỹ yêu cầu bài nộp từ giảng viên, làm rõ các thuật ngữ cốt lõi: High-stakes, Failure mode, Layer (UX, Grounding, Safety, Model), Harm và Human-in-the-loop.
- **Tương tác với AI**: Yêu cầu AI làm rõ sự khác biệt giữa các lớp lỗi (Layer) để phân loại chính xác nguồn gốc lỗi của từng case thay vì gộp chung vào lỗi mô hình.
- **Kết quả**: Thống nhất cấu trúc bài báo cáo tập trung trong tệp `README.md` theo định dạng Markdown khoa học, mạch lạc, dễ chấm trực tiếp trên GitHub.

### Giai đoạn 2: Xây dựng Industry Risk Snapshot
- **Nội dung**: Đánh giá toàn diện rủi ro của ngành HR Tech và tuyển dụng tự động.
- **Phản biện của AI**: AI nhắc nhở nhấn mạnh cơ sở pháp lý quốc tế (EU AI Act xếp HR AI vào nhóm High-Risk, EEOC Title VII, NYC Local Law 144) và lý giải vì sao dữ liệu tuyển dụng mang tính high-stakes đối với quyền lợi sinh kế của người lao động.
- **Đóng góp của học viên**: Đưa vào thực trạng xử lý dữ liệu PII trong CV và chỉ rõ các rủi ro phân biệt đối xử ngầm qua các trường dữ liệu gián tiếp (proxy attributes).

### Giai đoạn 3: Nghiên cứu 3 Brief Cases có thật với số liệu và nguồn chính thống
- **Nội dung**: Lựa chọn 3 trường hợp đại diện cho 3 kiểu thất bại khác nhau trong cùng ngành Tuyển dụng:
  1. *Amazon AI Recruiting Tool*: Thiên lệch giới tính do dữ liệu quá khứ (Historical Bias in Model/Grounding).
  2. *HireVue Video Assessment*: Suy diễn ngụy khoa học qua nét mặt, gây bất lợi cho người khuyết tật và đa văn hóa (Pseudoscience in Model/UX).
  3. *iTutorGroup Lawsuit*: Cài đặt quy tắc phân biệt đối xử trực tiếp theo độ tuổi, vi phạm pháp luật liên bang (Rule-based Bias in Safety/Grounding).
- **Kiểm chứng nguồn**: Tra cứu số liệu bồi thường cụ thể (365.000 USD trong vụ kiện của EEOC đối với iTutorGroup), mốc thời gian Amazon hủy bỏ dự án (đầu năm 2018), và tuyên bố gỡ bỏ tính năng nhận diện khuôn mặt của HireVue (tháng 01/2021) từ các báo cáo báo chí và thông cáo báo chí của cơ quan quản lý.

### Giai đoạn 4: Hoàn thiện Harm Map Worksheet và kết nối dự án P-092
- **Nội dung**: Lập bảng phân tích 5 trường thông tin chi tiết cho từng case; rút ra 4 nguyên tắc phòng ngừa rủi ro then chốt cho hệ thống Clear Hire.
- **Phản biện của AI**: AI gợi ý làm rõ chốt chặn kỹ thuật (Blind Screening, Evidence Citation) kết hợp với chốt chặn con người (Human-in-the-Loop tại thời điểm duyệt shortlist, không cho phép auto-reject).
- **Kết quả**: Bảng phân tích chi tiết, mạch lạc, chỉ rõ vai trò của từng vị trí nhân sự kiểm tra và thời điểm can thiệp.

---

## 3. Tổng kết vai trò
- **AI hỗ trợ**: Cung cấp khung phân tích, hỗ trợ tổng hợp thông tin sự kiện lịch sử, tra cứu văn bản pháp lý liên quan và định dạng bảng biểu.
- **Bản thân em**: Trực tiếp lựa chọn ca nghiên cứu phù hợp với bài toán của dự án P-092, thẩm định độ chính xác của các phân tích tác hại, xây dựng liên hệ thực tế và phê duyệt toàn bộ nội dung báo cáo nộp bài.
