# Lab 21 — Phân tích rủi ro AI qua case study thực tế
- Họ và tên: Chu Thùy Dương
- MSSV / mã học viên: 2A202602660
- Ngành đã chọn: HR / tuyển dụng

### 1. Industry Risk Snapshot
| Nội dung | Đánh giá của tôi và lý do |
| --- | --- |
| Những tác hại chính có thể xảy ra | Ứng viên mất cơ hội việc làm do thuật toán thiên lệch giới tính, tuổi tác hoặc suy diễn thiếu căn cứ từ nét mặt và giọng nói. Doanh nghiệp đối mặt rủi ro pháp lý, tổn hại uy tín và bỏ lỡ nhân tài. Ngoài ra còn có rủi ro lộ dữ liệu hồ sơ cá nhân và thiếu minh bạch khiến người dùng không thể khiếu nại |
| Mức độ high-stakes | Cao. Quyết định tuyển dụng ảnh hưởng trực tiếp đến thu nhập, sinh kế và cơ hội nghề nghiệp của một người. Khi triển khai ở quy mô lớn, thuật toán sai lệch có thể loại bỏ có hệ thống nhiều nhóm ứng viên mà họ không hề hay biết. Các quy định như Đạo luật AI của châu Âu hay hướng dẫn của EEOC Mỹ đều xếp việc làm vào nhóm rủi ro cao cần kiểm soát chặt |
| Dữ liệu nhạy cảm có thể được sử dụng | Hồ sơ ứng tuyển chứa nhiều thông tin cá nhân như họ tên, ngày sinh, địa chỉ, số điện thoại, trường học, hình ảnh và giọng nói trong video phỏng vấn. Các dữ liệu này dễ làm lộ gián tiếp giới tính, độ tuổi, tình trạng sức khỏe hoặc nguồn gốc xuất thân của ứng viên |
| Nhu cầu human review | Cao. Chuyên viên nhân sự và quản lý chuyên môn bắt buộc phải kiểm tra ở khâu duyệt danh sách phỏng vấn, xem xét các hồ sơ cận điểm chuẩn và ký duyệt từ chối. Tuyệt đối không để AI tự động loại hồ sơ mà không có người thẩm định lại lý do. |

### 2. Case study 1 — Amazon AI Recruiting Tool
#### Brief Case
- Tổ chức / sản phẩm AI: Amazon
- Thời gian, địa điểm / bối cảnh: Thử nghiệm từ năm 2014 đến 2017 tại trung tâm kỹ thuật của Amazon ở Edinburgh, Scotland, áp dụng cho vị trí kỹ sư phần mềm.
- AI được dùng để làm gì: Chấm điểm hồ sơ từ 1 đến 5 sao để tự động chọn ứng viên tiềm năng mời phỏng vấn, giúp giảm tải thời gian lọc hồ sơ thủ công.
- Vấn đề hoặc sự kiện đáng chú ý: Hệ thống bị thiên lệch giới tính đối với ứng viên nữ. Dữ liệu huấn luyện là hồ sơ nộp vào Amazon trong 10 năm trước đó, chủ yếu là nam giới, nên mô hình tự học rằng hồ sơ nam giới là chuẩn tuyển dụng. AI tự động trừ điểm các hồ sơ có từ phụ nữ như đội trưởng câu lạc bộ cờ vua nữ hoặc hồ sơ từ các trường đại học nữ sinh. Nhóm kỹ sư cố gắng sửa từ khóa nhưng mô hình vẫn tìm các đặc trưng khác để phân biệt, dẫn đến việc Amazon phải hủy bỏ dự án vào đầu năm 2018.
- Số liệu có nguồn: Dự án thử nghiệm khoảng 500 mô hình trên kho hồ sơ 10 năm của Amazon. Phát hiện lỗi năm 2015 và chính thức bị hủy bỏ vào đầu năm 2018 theo điều tra của Reuters ngày 10/10/2018.
- Nguồn: Reuters, tác giả Jeffrey Dastin, bài viết Amazon scraps secret AI recruiting tool that showed bias against women, ngày 10/10/2018. URL: https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G
- Phân biệt bằng chứng và nhận định:
  - Điều nguồn xác nhận: Reuters xác nhận Amazon thử nghiệm từ 2014, phát hiện thiên lệch năm 2015 và hủy dự án đầu năm 2018. Người phát ngôn Amazon khẳng định công cụ chưa từng dùng độc lập để ra quyết định tuyển dụng cuối cùng.
  - Điều tôi suy luận hoặc còn chưa rõ: Chưa có số liệu thống kê công khai về số lượng hồ sơ nữ thực tế bị chấm điểm thấp trong các đợt chạy thử nội bộ.

#### Harm Map Worksheet
| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | Thời điểm mô hình tự động chấm điểm sao và đề xuất danh sách ứng viên đủ điều kiện phỏng vấn cho chuyên viên nhân sự. |
| Stakeholder bị ảnh hưởng | Ứng viên nữ nộp hồ sơ, chuyên viên nhân sự bị định hướng sai, tập đoàn Amazon và cộng đồng lao động nữ trong ngành công nghệ. |
| Failure mode | Bias / fairness, kết hợp over-reliance khi nhân sự quá tin vào điểm sao của máy. |
| Layer bắt đầu lỗi | Grounding và Model. Dữ liệu quá khứ 10 năm bị lệch mẫu nam giới áp đảo; mô hình tự học tương quan ngầm để trừ điểm ứng viên nữ mà không có ràng buộc công bằng. |
| Harm xảy ra là gì? | Ứng viên nữ bị tước cơ hội phỏng vấn khi hệ thống hạ điểm hồ sơ có từ ngữ liên quan đến phụ nữ; Amazon lãng phí nhiều năm nghiên cứu và chịu tổn hại uy tín khi sự việc được công bố. |
| Harm lens | Opportunity loss và dignity loss. |
| Severity | High. Quyết định tuyển dụng tác động trực tiếp đến cơ hội việc làm và thu nhập của ứng viên. |
| Scale | Medium đến High. Trong nội bộ có 500 mô hình thử nghiệm trên hàng chục nghìn hồ sơ; nếu đưa vào áp dụng chính thức sẽ ảnh hưởng đến hàng trăm nghìn ứng viên toàn cầu mỗi năm. |
| Probability | High. Theo Reuters, mô hình gần như luôn trừ điểm các hồ sơ có từ khóa phụ nữ do trọng số đã học. |
| Frequency | High. Xuất hiện lặp lại trong mọi đợt chạy quét hồ sơ của ứng viên nữ. |
| Vì sao? | Mức nghiêm trọng là High vì liên quan đến việc làm. Quy mô dựa trên con số 500 mô hình thử nghiệm của Amazon. Xác suất và tần suất cao vì thuật toán chạy theo quy luật cố định. Giới hạn bằng chứng là Amazon không công bố số hồ sơ nữ cụ thể bị ảnh hưởng. |

### 3. Case study 2 — HireVue Video Interview Facial Analysis
#### Brief Case
- Tổ chức / sản phẩm AI: HireVue
- Thời gian, địa điểm / bối cảnh: Áp dụng tại Mỹ và quốc tế từ năm 2014 đến 2020, gây tranh cãi mạnh giai đoạn 2019-2021.
- AI được dùng để làm gì: Phân tích biểu cảm khuôn mặt, chuyển động mắt và giọng nói qua video phỏng vấn để tính điểm khả năng làm việc của ứng viên trước vòng nhân sự.
- Vấn đề hoặc sự kiện đáng chú ý: Đánh giá thiếu cơ sở khoa học và gây bất lợi lớn cho người khuyết tật, người tự kỷ hoặc người có biểu cảm khuôn mặt khác biệt do văn hóa. Những người có tật máy cơ mặt hoặc ít nhìn thẳng vào camera bị AI chấm điểm thấp vì cho là thiếu tự tin. Tổ chức EPIC khiếu nại lên Ủy ban Thương mại Liên bang Mỹ FTC năm 2019. Đến tháng 1/2021, HireVue phải bỏ hoàn toàn tính năng phân tích khuôn mặt.
- Số liệu có nguồn: Hơn 700 doanh nghiệp sử dụng, xử lý hơn 1 triệu cuộc phỏng vấn cho riêng Unilever và hàng triệu lượt trên toàn cầu theo Washington Post. Ngày 18/01/2021, HireVue thông báo loại bỏ 100% tính năng phân tích khuôn mặt theo bài báo của Wired.
- Nguồn:
  - Washington Post, tác giả Drew Harwell, ngày 22/10/2019. URL: https://www.washingtonpost.com/technology/2019/10/22/ai-hiring-face-scanning-algorithm-increasingly-decides-whether-you-deserve-job/
  - Đơn khiếu nại của EPIC gửi FTC, ngày 06/11/2019. URL: https://epic.org/documents/in-re-hirevue/
  - Wired, tác giả Tom Simonite, ngày 18/01/2021. URL: https://www.wired.com/story/hirevue-drops-facial-monitoring-amid-backlash/
- Phân biệt bằng chứng và nhận định:
  - Điều nguồn xác nhận: Các nguồn xác nhận HireVue dùng thuật toán phân tích nét mặt để chấm điểm, bị khiếu nại lên FTC, bị kiểm toán độc lập ORCAA đánh giá thiếu độ tin cậy và đã gỡ tính năng này đầu năm 2021.
  - Điều tôi suy luận hoặc còn chưa rõ: Chưa có số liệu thống kê công khai về số lượng ứng viên khuyết tật cụ thể đã bị loại trong thực tế do doanh nghiệp bảo mật dữ liệu tuyển dụng.

#### Harm Map Worksheet
| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | Khi thị giác máy tính quét video để tính điểm biểu cảm khuôn mặt và xếp hạng ứng viên trong vòng sơ tuyển. |
| Stakeholder bị ảnh hưởng | Ứng viên khuyết tật, người mắc chứng tự kỷ, ứng viên nói tiếng Anh không phải tiếng mẹ đẻ, doanh nghiệp tuyển dụng và công ty HireVue. |
| Failure mode | Bias / fairness kết hợp harmful advice khi AI cho điểm năng lực dựa trên đặc điểm hình thể không liên quan. |
| Layer bắt đầu lỗi | Model và UX. Mô hình gán ghép cử động cơ mặt với năng lực mà thiếu căn cứ khoa học; giao diện phỏng vấn video tự động không có tùy chọn hỗ trợ thay thế cho người khuyết tật. |
| Harm xảy ra là gì? | Ứng viên khuyết tật hoặc có phản xạ cơ mặt khác biệt bị đánh rớt oan và tổn thương tâm lý; doanh nghiệp đối mặt rủi ro pháp lý và mất ứng viên phù hợp. |
| Harm lens | Opportunity loss, dignity loss và misinformation. |
| Severity | High. Tước bỏ cơ hội việc làm dựa trên đặc điểm ngoại hình hoặc phản xạ cơ thể ngoài ý muốn. |
| Scale | High. Hơn 700 tập đoàn sử dụng, xử lý hàng triệu cuộc phỏng vấn video theo số liệu từ báo chí. |
| Probability | High. Theo đánh giá của kiểm toán thuật toán, người có biểu cảm khác biệt rất dễ bị điểm thấp vì hệ thống chuẩn hóa theo nhóm đa số. |
| Frequency | High. Xuất hiện trên mọi cuộc phỏng vấn video có bật tính năng phân tích khuôn mặt trước năm 2021. |
| Vì sao? | Mức nghiêm trọng là High vì tước đoạt cơ hội bình đẳng của người khuyết tật. Quy mô là High dựa trên số liệu 700 công ty và hàng triệu video. Giới hạn bằng chứng là HireVue không công bố số ứng viên bị đánh rớt cụ thể. |

### 4. Case study 3 — iTutorGroup Age Discrimination Software
#### Brief Case
- Tổ chức / sản phẩm AI: iTutorGroup
- Thời gian, địa điểm / bối cảnh: Giai đoạn 2020-2022 tại Mỹ, vụ kiện do Ủy ban Cơ hội Việc làm Bình đẳng Mỹ EEOC thụ lý tại Tòa án Quận Đông New York.
- AI được dùng để làm gì: Tự động lọc hồ sơ ứng viên đăng ký dạy tiếng Anh trực tuyến nộp qua cổng tuyển dụng.
- Vấn đề hoặc sự kiện đáng chú ý: Phần mềm cài đặt điều kiện tự động từ chối ứng viên nữ từ 55 tuổi trở lên và ứng viên nam từ 60 tuổi trở lên ngay khi họ điền ngày sinh. Một ứng viên bị từ chối đã nộp lại hồ sơ y hệt nhưng đổi năm sinh trẻ hơn thì lập tức được mời phỏng vấn. EEOC khởi kiện vì vi phạm luật chống phân biệt tuổi tác trong lao động. Tháng 8/2023, công ty chấp thuận nộp phạt để hòa giải.
- Số liệu có nguồn: Hơn 200 ứng viên đủ tiêu chuẩn bị hệ thống tự động từ chối vì tuổi tác. Ngày 09/08/2023, iTutorGroup đồng ý bồi thường 365.000 USD và chịu 5 năm giám sát theo thông cáo của EEOC.
- Nguồn:
  - Thông cáo báo chí của EEOC ngày 09/08/2023. URL: https://www.eeoc.gov/newsroom/itutorgroup-pay-365000-settle-eeoc-discriminatory-ai-lawsuit
  - Hồ sơ tòa án số 1:22-cv-02565-PKC-PK tại Tòa án Quận Đông New York.
  - Bloomberg Law, tháng 8/2023.
- Phân biệt bằng chứng và nhận định:
  - Điều nguồn xác nhận: EEOC và hồ sơ tòa án xác nhận hệ thống tự động từ chối hơn 200 ứng viên lớn tuổi và công ty đã nộp phạt 365.000 USD để hòa giải.
  - Điều tôi suy luận hoặc còn chưa rõ: Chưa rõ điều kiện lọc tuổi do chủ ý của bộ phận nhân sự hay do bên phát triển phần mềm cài đặt ngầm để tối ưu chi phí.

#### Harm Map Worksheet
| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | Khi ứng viên gửi biểu mẫu xin việc có ngày sinh và hệ thống tự động đưa ra quyết định từ chối ngay lập tức mà không có người xem xét. |
| Stakeholder bị ảnh hưởng | Ứng viên lớn tuổi bị mất việc, học viên mất cơ hội học với giáo viên có kinh nghiệm, công ty iTutorGroup bị phạt và cơ quan quản lý lao động. |
| Failure mode | Bias / fairness phân biệt đối xử theo độ tuổi, kết hợp escalation failure khi hệ thống không chuyển hồ sơ cho con người xử lý. |
| Layer bắt đầu lỗi | Safety và Grounding. Thiếu cơ chế kiểm soát an toàn để chặn điều kiện lọc vi phạm luật lao động; quy trình xử lý dùng năm sinh làm điều kiện loại trừ trực tiếp thay vì đánh giá chuyên môn. |
| Harm xảy ra là gì? | Hơn 200 ứng viên lớn tuổi bị tước cơ hội việc làm và thu nhập một cách bất công; công ty bị phạt 365.000 USD và chịu giám sát tư pháp trong 5 năm. |
| Harm lens | Opportunity loss và dignity loss. |
| Severity | High. Tước đoạt trực tiếp quyền làm việc của hơn 200 người và vi phạm pháp luật lao động. |
| Scale | Medium. Ảnh hưởng trực tiếp đến hơn 200 ứng viên nộp hồ sơ vào iTutorGroup theo số liệu của tòa án. |
| Probability | High. Xác suất bị loại là 100% đối với ứng viên trên ngưỡng tuổi vì đây là điều kiện lọc cố định trong mã nguồn. |
| Frequency | High. Lặp lại với mọi hồ sơ của ứng viên lớn tuổi gửi vào hệ thống trong thời gian áp dụng quy tắc. |
| Vì sao? | Mức nghiêm trọng là High vì xâm phạm quyền lợi việc làm chính đáng. Quy mô dựa trên số liệu chính thức hơn 200 người từ EEOC. Xác suất và tần suất cao vì quy tắc mang tính cơ học. Giới hạn bằng chứng là danh tính từng ứng viên được bảo mật trong thỏa thuận hòa giải. |