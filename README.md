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
| High-risk moment | Thời điểm mô hình học máy tự động chấm điểm xếp hạng (1 đến 5 sao) cho hồ sơ xin việc và tạo danh sách đề xuất ứng viên đạt tiêu chuẩn cho nhà tuyển dụng để quyết định mời phỏng vấn sơ loại. |
| Stakeholder bị ảnh hưởng | - Ứng viên nữ nộp đơn vào các vị trí kỹ sư phần mềm (người bị tác động trực tiếp).<br>- Chuyên viên tuyển dụng của Amazon (người dùng bị dẫn dắt bởi gợi ý thiên lệch).<br>- Tập đoàn Amazon (chịu tổn thất uy tín, lãng phí nguồn lực đầu tư).<br>- Cộng đồng phụ nữ trong ngành công nghệ (chịu bất bình đẳng kéo dài). |
| Failure mode | Bias / fairness (kết quả phân loại bất lợi và không công bằng đối với nhóm ứng viên nữ, kết hợp với Over-reliance khi nhà tuyển dụng có xu hướng tin tưởng vào xếp hạng sao của hệ thống). |
| Layer bắt đầu lỗi | Grounding & Model:<br>- *Grounding*: Tập dữ liệu huấn luyện (Training Data) thu thập trong 10 năm phản ánh thực trạng nam giới áp đảo trong quá khứ, khiến AI coi các đặc tính của nam giới là tiêu chuẩn thành công.<br>- *Model*: Thuật toán tối ưu hóa nhận diện các mối tương quan ngầm (proxy variables) để phạt điểm từ khóa liên quan đến phụ nữ mà không có ràng buộc về công bằng (fairness constraints). |
| Harm xảy ra là gì? | Ứng viên nữ bị tước đoạt cơ hội việc làm và phỏng vấn tại tập đoàn công nghệ khi hệ thống tự động trừ điểm các hồ sơ có từ khóa nữ giới; tập đoàn Amazon bị lãng phí 4 năm nghiên cứu và tổn hại uy tín thương hiệu khi sự cố bị phanh phui (đã xảy ra trong thử nghiệm nội bộ, ngăn chặn kịp thời trước khi đưa ra sản xuất). |
| Harm lens | Opportunity loss (mất cơ hội việc làm và thu nhập) và Dignity loss (tổn hại phẩm giá do bị đối xử bất công vì giới tính). |
| Severity | High. Quyết định tuyển dụng ảnh hưởng sâu sắc đến thu nhập, lộ trình sự nghiệp và an sinh của cá nhân, đồng thời củng cố rào cản bất bình đẳng giới trong ngành công nghệ cao (chưa đến mức Critical vì không gây tổn thương thể chất hay tử vong). |
| Scale | Medium đến High. Trong nội bộ Amazon, dự án chạy thử 500 mô hình trên hàng chục nghìn hồ sơ trong 10 năm. Nếu được đưa vào môi trường sản xuất chính thức, quy mô tác động sẽ lên tới hàng trăm nghìn ứng viên toàn cầu mỗi năm. |
| Probability | High (theo đánh giá cá nhân dựa trên phân tích kỹ thuật của Reuters): Mô hình mang tính tất định dựa trên trọng số đã học, do đó gần như 100% hồ sơ chứa từ khóa phụ nữ đều bị phạt điểm cho đến khi được kỹ sư can thiệp thủ công. |
| Frequency | High (theo đánh giá cá nhân): Xảy ra lặp đi lặp lại trong mọi lượt chạy quét hàng loạt (batch screening) đối với hồ sơ ứng viên nữ. |
| Vì sao? | - Đánh giá Severity là High vì tuyển dụng là quyết định có mức độ tác động cao (high-stakes) tới cơ hội sống và việc làm của con người.<br>- Đánh giá Probability và Frequency là High vì thuật toán tự động phạt điểm có tính hệ thống.<br>- Đánh giá Scale dựa trên quy mô thử nghiệm 500 mô hình của Amazon được Reuters ghi nhận.<br>- Giới hạn bằng chứng: Nguồn tin Reuters và Amazon không công bố số lượng tuyệt đối ứng viên nữ đã bị mô hình chấm điểm thấp trong các đợt chạy thử nội bộ. |

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
| High-risk moment | Thời điểm mô hình Computer Vision phân tích video phỏng vấn, tính toán điểm số biểu cảm khuôn mặt và xếp hạng ứng viên trong vòng sơ tuyển trước khi chuyên viên tuyển dụng có cơ hội tiếp xúc. |
| Stakeholder bị ảnh hưởng | - Ứng viên khuyết tật, người mắc chứng tự kỷ, rối loạn lo âu xã hội, hoặc có tật máy cơ mặt (bị phân biệt đối xử).<br>- Ứng viên đa văn hóa hoặc nói tiếng Anh không bản xứ (bị bất lợi do chuẩn mực giao tiếp mắt).<br>- Doanh nghiệp tuyển dụng (rủi ro vi phạm pháp luật lao động và bỏ lỡ ứng viên giỏi).<br>- Công ty HireVue (đối mặt khủng hoảng truyền thông và điều tra pháp lý). |
| Failure mode | Bias / fairness (phân biệt đối xử với ứng viên khuyết tật và khác biệt thần kinh) kết hợp Harmful advice (AI đưa ra điểm số đánh giá năng lực sai lệch dựa trên đặc điểm hình thể không liên quan). |
| Layer bắt đầu lỗi | Model & UX:<br>- *Model*: Thuật toán gán ghép tùy tiện cử động cơ mặt với năng lực làm việc mà không có căn cứ tâm lý học hay khoa học thần kinh hợp lệ.<br>- *UX*: Giao diện phỏng vấn video một chiều tạo áp lực cao, không cung cấp cơ chế hỗ trợ (accessibility options) hoặc hình thức thay thế cho ứng viên khuyết tật. |
| Harm xảy ra là gì? | Ứng viên khuyết tật hoặc có biểu cảm khuôn mặt dị biệt bị đánh rớt oan uổng và tổn thương tâm lý khi thuật toán Computer Vision quy chụp chuyển động cơ mặt với năng lực chuyên môn; doanh nghiệp tuyển dụng đối mặt rủi ro pháp lý và mất ứng viên tài năng (hậu quả thực tế đã diễn ra trong nhiều năm trước khi tính năng bị gỡ bỏ). |
| Harm lens | Opportunity loss (mất cơ hội việc làm), Dignity loss (tổn hại phẩm giá khi bị đánh giá năng lực qua ngoại hình), và Misinformation (hệ thống cung cấp điểm số sai lệch về năng lực ứng viên). |
| Severity | High. Tước đoạt cơ hội việc làm của ứng viên dựa trên đặc điểm thể chất ngoài ý muốn, gây tổn thương tâm lý và vi phạm nghiêm trọng quyền bình đẳng của người khuyết tật. |
| Scale | High. Hơn 700 tập đoàn lớn trên toàn cầu sử dụng hệ thống, xử lý hàng triệu cuộc phỏng vấn video của ứng viên trên toàn thế giới trong giai đoạn 2014–2020. |
| Probability | High (theo đánh giá cá nhân dựa trên phân tích của kiểm toán ORCAA): Khả năng một ứng viên có biểu cảm khuôn mặt khác thường bị chấm điểm thấp là rất cao do mô hình được chuẩn hóa theo biểu cảm của nhóm đa số. |
| Frequency | High. Diễn ra liên tục trong tất cả các cuộc phỏng vấn video có bật tính năng phân tích khuôn mặt trên nền tảng của HireVue trước tháng 01/2021. |
| Vì sao? | - Đánh giá Severity là High vì ảnh hưởng trực tiếp đến quyền bình đẳng và cơ hội việc làm của các nhóm yếu thế trong xã hội.<br>- Đánh giá Scale là High dựa trên số liệu thực tế được Washington Post và Wired ghi nhận (700+ doanh nghiệp, hàng triệu ứng viên).<br>- Đánh giá Probability và Frequency là High vì tính năng quét mặt chạy tự động trên mọi video nộp vào.<br>- Giới hạn bằng chứng: Số lượng cụ thể các ứng viên khuyết tật bị từ chối không được công bố công khai do chính sách bảo mật nội bộ của HireVue và các khách hàng doanh nghiệp. |

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
| High-risk moment | Thời điểm ứng viên gửi đơn xin việc trực tuyến có điền thông tin ngày tháng năm sinh, hệ thống kích hoạt logic lọc tự động và lập tức đưa ra quyết định từ chối hồ sơ (auto-rejection) mà không có sự xem xét của con người. |
| Stakeholder bị ảnh hưởng | - Ứng viên lớn tuổi (nữ từ 55 tuổi trở lên, nam từ 60 tuổi trở lên) bị tước đoạt cơ hội việc làm.<br>- Học sinh và phụ huynh (mất cơ hội học tập với giáo viên giàu kinh nghiệm sư phạm).<br>- Công ty iTutorGroup (bị phạt 365.000 USD, chịu giám sát tư pháp 5 năm, mất uy tín thương hiệu).<br>- Cơ quan quản lý EEOC (phải tiến hành điều tra và khởi kiện để bảo vệ công lý lao động). |
| Failure mode | Bias / fairness (phân biệt đối xử công khai và có chủ đích theo độ tuổi) kết hợp Escalation failure (hệ thống tự động loại bỏ dứt điểm mà không chuyển tiếp hồ sơ cho chuyên viên nhân sự kiểm tra). |
| Layer bắt đầu lỗi | Safety & Grounding:<br>- *Safety*: Hệ thống hoàn toàn thiếu vắng lớp rào chắn an toàn (Guardrails) để ngăn chặn việc cài đặt tiêu chí lọc vi phạm pháp luật lao động (Đạo luật ADEA cấm phân biệt tuổi tác từ 40 trở lên).<br>- *Grounding*: Logic nghiệp vụ của hệ thống sử dụng trường dữ liệu năm sinh làm điều kiện loại trừ tuyệt đối (hard filter) thay vì đánh giá năng lực giảng dạy. |
| Harm xảy ra là gì? | Hơn 200 ứng viên lớn tuổi đủ tiêu chuẩn bị hệ thống tự động từ chối trái pháp luật chỉ vì độ tuổi, làm mất sinh kế và tổn hại phẩm giá nghề nghiệp; công ty iTutorGroup bị phạt 365.000 USD và chịu 5 năm giám sát tư pháp (hậu quả thực tế đã được tòa án liên bang phán quyết). |
| Harm lens | Opportunity loss (mất cơ hội việc làm và thu nhập) và Dignity loss (tổn hại phẩm giá do bị phân biệt đối xử vì tuổi tác). |
| Severity | High. Tước đoạt trực tiếp quyền lợi lao động hợp pháp của hơn 200 con người, vi phạm trắng trợn luật pháp liên bang Hoa Kỳ về chống phân biệt đối xử trong việc làm. |
| Scale | Medium. Quy mô được xác định chính xác theo hồ sơ tòa án là hơn 200 ứng viên đủ tiêu chuẩn bị từ chối trực tiếp tại Hoa Kỳ trong giai đoạn công ty áp dụng thuật toán lọc này. |
| Probability | High / 100% (căn cứ vào phán quyết tòa án): Do đây là quy tắc cứng (hardcoded rule) được lập trình trong thuật toán, xác suất một ứng viên đạt ngưỡng tuổi bị tự động từ chối là 100% khi điền đúng năm sinh. |
| Frequency | High. Lặp lại tuyệt đối đối với mọi hồ sơ của ứng viên lớn tuổi nộp vào hệ thống trong suốt thời gian quy tắc lọc này hoạt động. |
| Vì sao? | - Đánh giá Severity là High vì xâm phạm quyền dân sự và cơ hội sinh kế chính đáng của người lao động.<br>- Đánh giá Scale dựa trên con số chính thức hơn 200 ứng viên trong thông cáo báo chí của EEOC và phán quyết của Tòa án Liên bang Quận Đông New York.<br>- Đánh giá Probability và Frequency là 100% / High vì quy tắc lọc mang tính cơ học, không có độ ngẫu nhiên.<br>- Giới hạn bằng chứng: Hồ sơ công khai không nêu rõ danh tính cá nhân từng ứng viên để bảo vệ quyền riêng tư theo thỏa thuận hòa giải (Consent Decree). |
