# Lab 21 — Phân tích rủi ro AI qua case study thực tế
- Họ và tên: Chu Thùy Dương
- MSSV / mã học viên: 2A202602660
- Lớp: Track 1
- Ngành đã chọn: Tuyển dụng & Quản trị Nhân sự (HR Tech / AI Recruitment)

### 1. Industry Risk Snapshot
| Nội dung | Đánh giá của tôi và lý do |
| --- | --- |
| Những tác hại chính có thể xảy ra | Phân biệt đối xử thuật toán (thiên lệch giới tính, độ tuổi, khuyết tật) tước đoạt cơ hội việc làm của ứng viên; ảo giác hoặc suy diễn ngụy khoa học (đo năng lực qua cơ mặt, giọng nói); mất tính minh bạch khiến ứng viên không thể khiếu nại; rò rỉ dữ liệu cá nhân (CV, video) và xâm phạm quyền riêng tư. Đối tượng bị ảnh hưởng trực tiếp là ứng viên tìm việc (đặc biệt là các nhóm yếu thế), tiếp đến là doanh nghiệp tuyển dụng (rủi ro pháp lý, mất uy tín thương hiệu, bỏ lỡ nhân tài). |
| Mức độ high-stakes | Cao. Quyết định tuyển dụng ảnh hưởng trực tiếp đến sinh kế, thu nhập, an sinh xã hội và lộ trình sự nghiệp của cá nhân. Ở quy mô lớn, một lỗi thiên lệch thuật toán có thể loại bỏ có hệ thống hàng nghìn ứng viên thuộc một nhóm nhân khẩu học. Các khung pháp lý toàn cầu (như EU AI Act Phụ lục III, EEOC Hoa Kỳ, NYC Local Law 144) đều xếp các công cụ AI hỗ trợ quyết định việc làm vào nhóm rủi ro cao cần giám sát nghiêm ngặt. |
| Dữ liệu nhạy cảm có thể được sử dụng | Dữ liệu định danh cá nhân (PII: họ tên, số điện thoại, email, địa chỉ cư trú, căn cước); các đặc tính nhân khẩu học được pháp luật bảo vệ (tuổi tác, giới tính, chủng tộc, tình trạng hôn nhân, tôn giáo — thường bộc lộ qua trường đại học, tên hội nhóm); dữ liệu sinh trắc học và sức khỏe (hình ảnh khuôn mặt, khẩu hình, tần số giọng nói từ video interview; thông tin khuyết tật hoặc khoảng trống nghề nghiệp trong CV); lịch sử thu nhập và vị thế kinh tế - xã hội. |
| Nhu cầu human review | Cao. Chuyên viên tuyển dụng (Recruiter), Trưởng bộ phận chuyên môn (Hiring Manager) và Cán bộ tuân thủ (Compliance Officer) bắt buộc phải kiểm tra ở các bước chốt danh sách sơ loại (shortlist), xem xét 100% các ca giáp ranh (borderline), và phê duyệt quyết định từ chối. Vì AI dễ mắc lỗi thiên lệch ngầm hoặc ảo giác trích xuất, nếu cho phép AI tự động từ chối (auto-reject) mà không có con người giám sát và giải trình sẽ dẫn đến vi phạm pháp luật và gây thiệt hại bất công cho ứng viên. |

### 2. Case study 1 — Amazon AI Recruiting Tool
#### Brief Case
- Tổ chức / sản phẩm AI: Amazon.com Inc. / Dự án công cụ học máy sàng lọc CV nội bộ (Amazon Machine Learning Recruiting Tool).
- Thời gian, địa điểm / bối cảnh: 2014–2017 tại trung tâm công nghệ của Amazon ở Edinburgh, Scotland; thử nghiệm cho các vị trí kỹ sư phát triển phần mềm (Software Development Engineers).
- AI được dùng để làm gì: Tự động chấm điểm hồ sơ ứng viên từ 1 đến 5 sao để tìm ra top ứng viên xuất sắc nhất và mời phỏng vấn, nhằm giảm tải công việc lọc tay hàng nghìn hồ sơ của chuyên viên nhân sự.
- Vấn đề hoặc sự kiện đáng chú ý: Mô hình bị thiên lệch giới tính chống lại ứng viên nữ (Severe Gender Bias). Do dữ liệu huấn luyện lấy từ CV nộp vào Amazon trong 10 năm trước đó (ngành công nghệ vốn có tỷ lệ nam giới áp đảo), AI tự học quy luật ngầm rằng nam giới là ứng viên ưu tiên. Hệ thống tự động trừ điểm các CV có chứa từ "women's" (ví dụ: "women's chess club captain") và hạ điểm ứng viên tốt nghiệp từ các trường đại học nữ sinh. Nhóm kỹ sư phát hiện năm 2015 và sửa các từ khóa, nhưng mô hình vẫn tiếp tục tự học các biến đại diện (proxy variables) khác để phân biệt giới. Dự án chính thức bị hủy bỏ và giải thể vào đầu năm 2018.
- Số liệu có nguồn: Khoảng 500 mô hình máy tính được huấn luyện cho các vị trí công việc cụ thể dựa trên tập dữ liệu hồ sơ xin việc tích lũy trong 10 năm tại Amazon. Dự án thử nghiệm từ năm 2014, phát hiện thiên lệch năm 2015, và bị hủy bỏ hoàn toàn vào đầu năm 2018 theo điều tra độc lập của Reuters công bố ngày 10/10/2018.
- Nguồn: Bài báo *"Amazon scraps secret AI recruiting tool that showed bias against women"* — Hãng thông tấn Reuters — Tác giả Jeffrey Dastin — Ngày công bố: 10/10/2018 — URL: https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G
- Phân biệt bằng chứng và nhận định:
  - *Điều nguồn xác nhận*: Reuters xác nhận Amazon đã thử nghiệm hệ thống từ 2014, phát hiện bias năm 2015 (hạ điểm từ khóa 'women's' và trường nữ sinh), đã giải thể nhóm dự án vào đầu năm 2018; người phát ngôn Amazon khẳng định công cụ chưa từng được dùng độc lập để ra quyết định tuyển dụng cuối cùng.
  - *Điều tôi suy luận hoặc còn chưa rõ*: Chưa rõ tỷ lệ chính xác ứng viên nữ bị loại bỏ thực tế trong giai đoạn chạy thử nội bộ (Amazon không công bố số lượng cụ thể CV bị tác động trong quá trình thử nghiệm).

#### Harm Map Worksheet
| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | [Tình huống cụ thể có rủi ro] |
| Stakeholder bị ảnh hưởng | [Người dùng và các bên liên quan] |
| Failure mode | [Kiểu lỗi AI] |
| Layer bắt đầu lỗi | [UX / Grounding / Safety / Model; giải thích hoặc ghi chưa đủ bằng chứng] |
| Harm xảy ra là gì? | [Ai bị ảnh hưởng + hậu quả; ghi rõ đã xảy ra hay mới là nguy cơ] |
| Harm lens | [Loại tác hại] |
| Severity | [Low / Medium / High / Critical] |
| Scale | [Quy mô tác động và căn cứ] |
| Probability | [Khả năng xảy ra và căn cứ] |
| Frequency | [Tần suất và căn cứ] |
| Vì sao? | [Lý do cho các đánh giá; nguồn hoặc giới hạn bằng chứng] |

### 3. Case study 2 — HireVue Video Interview Facial Analysis
#### Brief Case
- Tổ chức / sản phẩm AI: HireVue Inc. / Tính năng phân tích cử động khuôn mặt và giọng nói trong phỏng vấn video (HireVue AI Video Assessment with Facial Monitoring).
- Thời gian, địa điểm / bối cảnh: Áp dụng tại Mỹ và toàn cầu giai đoạn 2014–2020 cho hàng trăm doanh nghiệp; đỉnh điểm gây tranh cãi và khiếu nại pháp lý giai đoạn 2019–2021.
- AI được dùng để làm gì: Phân tích biểu cảm cơ mặt (micro-expressions), chuyển động mắt và ngữ điệu giọng nói trong video trả lời phỏng vấn sơ loại để tự động tính điểm "khả năng tuyển dụng" (employability score) và xếp hạng ứng viên trước khi chuyên viên tuyển dụng xem video.
- Vấn đề hoặc sự kiện đáng chú ý: Thiếu căn cứ khoa học vững chắc (ngụy khoa học diện mạo học / physiognomy) và gây thiên lệch nghiêm trọng đối với người khuyết tật, người mắc chứng tự kỷ / lo âu xã hội (neurodivergent), và người nói tiếng Anh phi bản xứ. Cử động cơ mặt bất thường hoặc thiếu giao tiếp bằng mắt (eye contact) bị AI đánh giá là "thiếu tự tin", "kém hòa nhập". Tổ chức EPIC đệ đơn khiếu nại lên FTC năm 2019 cáo buộc thực hành thương mại lừa dối và không công bằng. Kiểm toán ORCAA năm 2020 chỉ ra tính năng này thiếu cơ sở dự đoán năng lực. HireVue buộc phải gỡ bỏ hoàn toàn tính năng này vào tháng 01/2021.
- Số liệu có nguồn: Được sử dụng bởi hơn 700 công ty toàn cầu (bao gồm Unilever, Hilton, Goldman Sachs), xử lý hơn 1 triệu cuộc phỏng vấn video cho Unilever đơn lẻ và hàng triệu cuộc trên toàn cầu tính đến năm 2019 (theo Washington Post). Tháng 11/2019, EPIC nộp đơn khiếu nại dài 23 trang lên FTC. Ngày 18/01/2021, HireVue chính thức thông báo loại bỏ hoàn toàn 100% tính năng phân tích khuôn mặt khỏi nền tảng (theo Wired).
- Nguồn:
  1. Bài báo *"A face-scanning algorithm increasingly decides whether you deserve the job"* — Tác giả Drew Harwell — Báo The Washington Post — 22/10/2019 — URL: https://www.washingtonpost.com/technology/2019/10/22/ai-hiring-face-scanning-algorithm-increasingly-decides-whether-you-deserve-job/
  2. Đơn khiếu nại *Complaint and Request for Investigation In Re HireVue, Inc.* — Tổ chức EPIC — 06/11/2019 — URL: https://epic.org/documents/in-re-hirevue/
  3. Bài báo *"HireVue Drops Facial Monitoring Amid Backlash"* — Tác giả Tom Simonite — Tạp chí Wired — 18/01/2021 — URL: https://www.wired.com/story/hirevue-drops-facial-monitoring-amid-backlash/
- Phân biệt bằng chứng và nhận định:
  - *Điều nguồn xác nhận*: Các nguồn xác nhận HireVue đã sử dụng phân tích cử động khuôn mặt để chấm điểm, bị khiếu nại lên FTC vì hành vi thương mại thiếu công bằng, kiểm toán ORCAA chỉ ra rủi ro thiên lệch, và HireVue đã gỡ bỏ tính năng này vào tháng 01/2021.
  - *Điều tôi suy luận hoặc còn chưa rõ*: Chưa có số liệu định lượng công khai chính xác về số lượng ứng viên khuyết tật đã bị loại oan uổng trong suốt giai đoạn tính năng này vận hành, do dữ liệu chấm điểm là bảo mật độc quyền của các doanh nghiệp sử dụng.

#### Harm Map Worksheet
| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | [Điền] |
| Stakeholder bị ảnh hưởng | [Điền] |
| Failure mode | [Điền] |
| Layer bắt đầu lỗi | [Điền] |
| Harm xảy ra là gì? | [Điền; phân biệt hậu quả đã xảy ra với nguy cơ] |
| Harm lens | [Điền] |
| Severity | [Điền] |
| Scale | [Điền] |
| Probability | [Điền] |
| Frequency | [Điền] |
| Vì sao? | [Điền căn cứ và giới hạn bằng chứng] |

### 4. Case study 3 — iTutorGroup Age Discrimination Software
#### Brief Case
- Tổ chức / sản phẩm AI: iTutorGroup, Inc. (các công ty con thuộc tập đoàn Tutor Group / Ping An Insurance cung cấp nền tảng dạy tiếng Anh trực tuyến VIPABC và TutorABC).
- Thời gian, địa điểm / bối cảnh: Giai đoạn 2020–2022 tại Hoa Kỳ; vụ kiện của cơ quan liên bang EEOC được thụ lý tại Tòa án Quận Đông New York (E.D.N.Y.).
- AI được dùng để làm gì: Tự động sàng lọc hồ sơ ứng viên đăng ký làm giáo viên dạy tiếng Anh trực tuyến nộp qua cổng tuyển dụng trực tuyến của công ty.
- Vấn đề hoặc sự kiện đáng chú ý: Phân biệt đối xử theo độ tuổi bằng thuật toán trực tiếp (Explicit Algorithmic Age Discrimination). Phần mềm tuyển dụng được cài đặt quy tắc tự động từ chối ngay lập tức các ứng viên nữ từ 55 tuổi trở lên và ứng viên nam từ 60 tuổi trở lên ngay sau khi ứng viên điền ngày sinh, bất kể bằng cấp hay kinh nghiệm chuyên môn. Sự việc bị phát giác khi một ứng viên bị từ chối ngay tức khắc đã nộp lại một bộ hồ sơ y hệt nhưng chỉ sửa lại năm sinh trẻ hơn thì lập tức nhận được lời mời phỏng vấn ngay ngày hôm sau.
- Số liệu có nguồn: Hơn 200 ứng viên đủ tiêu chuẩn bị hệ thống tự động từ chối trái pháp luật chỉ vì độ tuổi (theo thông cáo của EEOC). Ngày 09/08/2023, iTutorGroup chấp thuận thỏa thuận hòa giải (Consent Decree), đồng ý bồi thường khoản tiền phạt 365.000 USD cho các ứng viên bị từ chối và chịu giám sát tư pháp trong 5 năm (theo Thông cáo báo chí của EEOC và Phán quyết vụ kiện số 1:22-cv-02565).
- Nguồn:
  1. Thông cáo báo chí *"iTutorGroup to Pay $365,000 to Settle EEOC Discriminatory AI Lawsuit"* — U.S. Equal Employment Opportunity Commission (EEOC) — Ngày 09/08/2023 — URL: https://www.eeoc.gov/newsroom/itutorgroup-pay-365000-settle-eeoc-discriminatory-ai-lawsuit
  2. Hồ sơ tòa án: Case No. 1:22-cv-02565-PKC-PK (U.S. District Court for the Eastern District of New York), Consent Decree ngày 09/08/2023.
  3. Bài báo *"AI Hiring Bias Lawsuit Settlement Marks First-of-Kind for EEOC"* — Bloomberg Law — Tháng 08/2023.
- Phân biệt bằng chứng và nhận định:
  - *Điều nguồn xác nhận*: EEOC xác nhận chính thức trên hồ sơ tòa án rằng hệ thống tuyển dụng tự động từ chối hơn 200 ứng viên dựa trên tuổi tác, vi phạm Đạo luật Chống phân biệt đối xử vì tuổi tác trong lao động (ADEA), và iTutorGroup đã chấp thuận nộp phạt 365.000 USD để hòa giải.
  - *Điều tôi suy luận hoặc còn chưa rõ*: Chưa rõ việc cài đặt quy tắc này xuất phát từ chỉ đạo chủ quan của bộ phận nhân sự hay từ thuật toán tối ưu hóa chi phí ngầm định của nhà cung cấp phần mềm, nhưng về mặt pháp lý và hệ thống, đây là lỗi vi phạm an toàn nghiêm trọng ở tầng Safety Layer và Logic nghiệp vụ.

#### Harm Map Worksheet
| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | [Điền] |
| Stakeholder bị ảnh hưởng | [Điền] |
| Failure mode | [Điền] |
| Layer bắt đầu lỗi | [Điền] |
| Harm xảy ra là gì? | [Điền; phân biệt hậu quả đã xảy ra với nguy cơ] |
| Harm lens | [Điền] |
| Severity | [Điền] |
| Scale | [Điền] |
| Probability | [Điền] |
| Frequency | [Điền] |
| Vì sao? | [Điền căn cứ và giới hạn bằng chứng] |
