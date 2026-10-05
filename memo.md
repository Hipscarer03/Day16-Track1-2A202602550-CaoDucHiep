# Memo Teardown — SPEAK (Speak App)

**Họ tên:** Cao Đức Hiệp (Mã học viên: 2A202602550)

**Vì sao chọn sản phẩm này:** Speak là case study điển hình nhất về việc một startup EdTech chuyển dịch thành công từ "AI wrapper" đơn thuần thành kỳ lân 1 tỷ USD nhờ sở hữu data flywheel (mô hình nhận diện giọng nói riêng) kết hợp với pedagogical workflow moat, đứng vững trước sức ép cạnh tranh trực diện từ các Big Tech và Foundation Model (OpenAI, Duolingo).

---

## §1. Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| **2019** | **Ra mắt tại Hàn Quốc:** Ưu tiên nói thành tiếng, học theo mẫu câu rồi lặp lại thay vì học thuộc từ vựng/ngữ pháp. Trọng tâm là ép học viên mở miệng phát âm càng nhiều càng tốt. <br>🔗 [TechCrunch 6/2024](https://techcrunch.com/2024/06/20/language-learning-app-speak-nets-20m-doubles-valuation/?rand=23331) | Thị trường học ngoại ngữ lúc đó còn lạ lẫm với AI; nhà đầu tư nghi ngờ việc thu thập giọng nói. Bản thử nghiệm 2017 mới chỉ nhận diện giọng nước ngoài cơ bản, chưa có hội thoại trọn vẹn, chưa có LLM. [Forbes](https://www.forbes.com/sites/rashishrivastava/2025/11/12/this-startup-is-racing-duolingo-to-replace-human-language-tutors-with-ai/) | **Định nghĩa "Tốt" & Vertical AI sơ khởi:** <br>- Định nghĩa "tốt" là **nói được trôi chảy**, không phải nhớ nhiều mẹo ngữ pháp.<br>- Tập trung dọc vào một năng lực cốt lõi: nhận diện giọng nói + phản xạ lặp mẫu câu. |
| **11/2022** | **Ra mắt AI Tutor trên GPT-3 (text-davinci-003):** Người dùng có thể hội thoại mở với AI như người thật theo các chủ đề và tình huống nhập vai linh hoạt. <br>🔗 [TechCrunch 11/2022](https://techcrunch.com/2022/11/17/openai-startup-fund-backs-language-learning-platform-speak-in-27m-round/) | Ra mắt chỉ vài ngày trước khi ChatGPT bùng nổ toàn cầu. Speak nhận đầu tư 27 triệu USD từ quỹ OpenAI Startup Fund, giúp tiếp cận sớm các model thử nghiệm tiên tiến nhất. | **Trải nghiệm x10:** <br>- Bước nhảy vọt từ việc lặp lại kịch bản cứng sang trò chuyện mở không giới hạn.<br>- Loại bỏ hoàn toàn nỗi sợ bị phán xét khi giao tiếp với giáo viên bản xứ bằng người thật. |
| **14/03/2023** | **Nâng cấp AI Tutor lên GPT-4:** Cá nhân hóa phản hồi ngữ pháp và phát âm theo ngữ cảnh sâu của người học. <br>🔗 [Speak Blog (GPT-4)](https://www.speak.com/blog/speak-gpt-4) | GPT-4 ra mắt. Đối thủ Duolingo cũng tung Duolingo Max (dùng GPT-4). Nguy cơ bị định danh là "wrapper mỏng" nếu chỉ gọi API OpenAI thông thường. Nhờ quỹ OpenAI, Speak đã thử nghiệm GPT-4 trước công chúng 2 tháng. | **Wrapper vs. Moat:** <br>- Model nền tảng ai cũng có thể mua được, nên LLM không phải moat độc quyền.<br>- Moat thực sự nằm ở pedagogical UX: cách nhúng phản hồi vào bài học và logic tinh chỉnh chuyên biệt cho sư phạm ngôn ngữ. |
| **2023 – 2024** | **Mở rộng quốc tế (Nhật Bản, Đài Loan) & Hyper-localization:** Tối ưu hóa bộ giải thích lỗi bằng tiếng mẹ đẻ của học viên từng nước (tăng tốc độ xử lý nhanh hơn 2,8 lần tại Nhật). <br>🔗 [Speak Blog (Series B-2)](https://www.speak.com/blog/series-b-2) | Trước đó ứng dụng phụ thuộc lớn vào thị trường Hàn Quốc. Mở rộng quốc tế đối mặt với rào cản tâm lý e ngại nói tiếng Anh và các lỗi phát âm đặc thù của người học từng vùng văn hóa Á Đông. | **Vertical AI & Domain Expertise:** <br>- Thấu hiểu rào cản tâm lý và cấu trúc lỗi phát âm đặc thù của từng dân tộc.<br>- AI đóng vai trò gia sư bản địa hóa sâu sắc, không áp dụng một kịch bản rập khuôn toàn cầu. |
| **H2/2024** | **Ra mắt Speak for Business (Pivot sang B2B Enterprise):** Cung cấp giải pháp đào tạo ngoại ngữ cho doanh nghiệp kèm Dashboard quản trị tiến độ nhân viên. <br>🔗 [Speak B2B](https://www.speak.com/b2b) | Tăng trưởng B2C bắt đầu chạm ngưỡng chi phí thu hút khách hàng (CAC) cao; doanh nghiệp toàn cầu có nhu cầu cấp bách nâng cao năng lực tiếng Anh thực chiến cho nhân viên. Đạt hơn 200 khách hàng doanh nghiệp với tỷ lệ sử dụng 85%. | **Moat từ Workflow & Đổi Segment:** <br>- Mở rộng từ B2C sang B2B tạo dòng tiền định kỳ (ARR) ổn định và giảm churn rate.<br>- Tạo switching cost cao nhờ tích hợp chặt chẽ vào quy trình đào tạo và KPI nhân sự của tổ chức. |
| **2024 (T6 & T12)** | **Chiến lược Đa ngôn ngữ (Tây Ban Nha, Pháp) & Tự huấn luyện Voice Model:** Nhận diện giọng nói bằng model riêng tự train trên dữ liệu nội bộ. Gọi vốn Series C 78M USD (định giá 1 tỷ USD). <br>🔗 [TechCrunch 12/2024](https://techcrunch.com/2024/12/10/openai-backed-speak-raises-78m-at-1b-valuation-to-help-users-learn-languages-by-talking-out-loud) | Thị trường người Mỹ học tiếng Tây Ban Nha vô cùng lớn. Việc phụ thuộc hoàn toàn vào Whisper/OpenAI gây tốn kém chi phí suy luận và độ trễ cao. Định giá tăng vọt từ 500M lên 1 tỷ USD sau 6 tháng. | **Data Flywheel & Proprietary Moat:** <br>- Moat bền vững nhất là mô hình nhận diện giọng nói tự huấn luyện trên hàng triệu giờ âm thanh phát âm lỗi của người học ngoại ngữ.<br>- Chuyển hóa từ "AI Wrapper" thành "Deep-tech AI Vertical Application". |
| **10/12/2025** | **Winter Release: Vòng lặp thích ứng (Adaptive Learning Loop) & Chuẩn hóa Speak Level:** Cấu trúc bài học theo chu trình Learn -> Practice -> Apply, ra mắt thước đo Speak Level cùng cơ chế streak freeze/repair. <br>🔗 [Speak Blog (Winter 2025)](https://www.speak.com/blog/winter-2025) | Thâm nhập thị trường Mỹ đối đầu trực diện Duolingo. Các voice bot đa dụng tràn lan khiến người dùng hoài nghi về tính hiệu quả nếu chỉ nói chuyện phiếm không có cấu trúc. | **Vòng Lặp Học (Learning Loop) & Định Nghĩa "Tốt":** <br>- Khép kín vòng lặp sư phạm: Học kiến thức mới $\rightarrow$ Luyện phản xạ $\rightarrow$ Ứng dụng nhập vai thực tế.<br>- "Speak Level" chuẩn hóa năng lực, cho học viên thấy rõ sự tiến bộ định lượng sau mỗi buổi học. |
| **~10/9/2026** | **Live Tutor Lessons trên GPT-Live-1 (Full-duplex Realtime Voice):** Gia sư đàm thoại hai chiều thời gian thực, cho phép ngắt lời, chen ngang tức thì không có độ trễ. <br>🔗 [X của Speak](https://x.com/speak/status/2098095986606551481) | OpenAI ra mắt mô hình GPT-Live (nghe-nói song công) vào tháng 7/2026 và mở API tháng 9/2026. Các hãng lớn đều đua voice bot real-time. Ranh giới giữa gia sư AI và gia sư người thật bị xóa nhòa. | **x10 Trải nghiệm & Định vị Moat Sư phạm:** <br>- Đạt bước nhảy vọt x10 về tính tự nhiên trong đàm thoại (zero-latency, interruptible).<br>- Tái khẳng định chiến lược: Khi model nền tảng ai cũng thuê được, moat của Speak nằm ở **ngữ cảnh bài học, hệ thống sửa lỗi sư phạm và thói quen tích lũy của người học**. |

**Vì sao chọn những mốc này:** Cả 8 cột mốc trên đều đánh dấu một **Quyết định Sản phẩm chiến lược (Strategic Product Decision)** làm biến đổi căn bản 1 trong 4 trụ cột: Giá trị cốt lõi (Value Prop), Rào cản phòng thủ (Moat), Khách hàng & Mô hình doanh thu (Segment/Business Model), hoặc Khung phương pháp sư phạm (Pedagogical Framework). Nhóm đã chủ động loại bỏ các mốc: (1) Cải tiến giao diện/thẩm mỹ thuần túy (UI redesign, dark mode); (2) Các chương trình khuyến mãi hay giảm giá ngắn hạn; (3) Các bản vá lỗi phần mềm nhỏ lẻ thường nhật.

---

## §2. Tệp user & JTBD

| Tiêu chí | Early Adopters (Seoul, 2019–2022) | Tệp Hiện Tại 1: B2B Enterprise (H2/2024–2026) | Tệp Hiện Tại 2: Người học Mỹ/Toàn cầu (2024–2026) |
|---|---|---|---|
| **Đặc điểm** | Dân công sở/chuyên viên tại Seoul (25–38 tuổi). Nắm chắc ngữ pháp qua thi cử (TOEIC/CSAT) nhưng bị "câm tiếng Anh" vì sợ sai và thiếu môi trường nói. Sẵn sàng trả phí để cải thiện sự nghiệp. | Quản lý L&D, Giám đốc Nhân sự (người mua) & Nhân viên văn phòng tập đoàn đa quốc gia tại Hàn, Nhật, Đài Loan, Mỹ (người dùng cuối). | Người lớn tại Mỹ (20–45 tuổi) học tiếng Tây Ban Nha / Pháp phục vụ công việc, du lịch, giao tiếp cộng đồng; hoặc người học toàn cầu muốn vượt qua phản xạ ngập ngừng. |
| **JTBD chính** | *"Khi cần thăng tiến hoặc phỏng vấn công ty đa quốc gia, hãy giúp tôi luyện nói phản xạ thành tiếng mỗi ngày mà không bị xấu hổ hay phán xét, để tôi tự tin mở miệng khi giao tiếp thực tế."* | *"Là doanh nghiệp, hãy giúp chúng tôi chuẩn hóa và nâng cao năng lực giao tiếp tiếng Anh cho toàn thể nhân sự với chi phí thấp hơn thuê gia sư và có dashboard đo lường ROI/tiến độ đào tạo rõ ràng."* | *"Khi cần giao tiếp thực tế với đồng nghiệp hoặc người bản xứ, hãy giúp tôi luyện phản xạ nghe-nói tự nhiên theo nhịp sống bận rộn, thay vì chỉ bấm chọn trắc nghiệm từ vựng như app cũ."* |
| **Trước đó họ làm bằng cách nào** | Học trung tâm ngoại ngữ (hagwon), thuê gia sư 1-kèm-1 qua video call (Cambly, Ringle) tốn kém và áp lực tâm lý, hoặc chỉ cày đề ngữ pháp tĩnh. | Mua các khóa học e-learning thụ động (tỷ lệ hoàn thành <10%), hoặc thuê giáo viên bản ngữ dạy nhóm đắt đỏ nhưng khó giám sát kết quả từng nhân sự. | Dùng Duolingo (chỉ bấm quẹt từ, không nói được thành câu), mua giáo trình tự học, hoặc dùng thử ChatGPT Voice nhưng thiếu bài bản dẫn dắt. |

### Dịch chuyển tệp: Cột mốc nào ở §1 gây ra sự dịch chuyển? Tại sao?
1. **Mốc H2/2024 (Ra mắt Speak for Business):** Chuyển dịch căn bản mô hình từ B2C (người dùng tự bỏ tiền túi, thói quen dễ bị đứt quãng) sang B2B Enterprise (doanh nghiệp trả tiền, tích hợp vào KPI nội bộ). Sự dịch chuyển này giải quyết bài toán CAC cao của B2C và mang lại nguồn doanh thu định kỳ lớn với tỷ lệ duy trì cao.
2. **Mốc 2024 (Đa ngôn ngữ Tây Ban Nha/Pháp & Mở rộng sang Mỹ):** Đưa Speak vượt ra khỏi ngách "người Đông Á học tiếng Anh" để bước vào thị trường ngoại ngữ lớn nhất phương Tây (người Mỹ học tiếng Tây Ban Nha), đối đầu trực tiếp với Duolingo trên sân nhà đối thủ.

### Switching Cost (Map 4 Forces): Điều gì giữ user ở lại? Lực nào đang kéo họ đi / giữ họ lại?

`mermaid
flowchart TD
    subgraph ThucDay["LỰC THÚC ĐẨY CHUYỂN DỊCH (Promoting Change)"]
        Push["1. PUSH (Lực Đẩy)<br>Thất vọng với app cũ; bức xúc khi AI chấm sai âm ngắn"]
        Pull["2. PULL (Lực Kéo)<br>Ép nói x10; không bị phán xét; AI Live tương tác song công"]
    end
    subgraph CanTro["LỰC CẢN TRỞ CHUYỂN DỊCH (Inhibiting Change)"]
        Anxiety["3. ANXIETY (Lo Ngại)<br>Ma sát trừ tiền Trial; sợ mất lộ trình Speak Level"]
        Habit["4. HABIT (Thói Quen)<br>B2C: Thói quen lỏng lẻo<br>B2B: Khóa chân bằng quy trình doanh nghiệp"]
    end
`

- **1. PUSH (Lực đẩy):** 
  - *Từ cách học cũ:* Bức xúc vì học Duolingo nhiều năm vẫn "câm tiếng Anh"; áp lực tâm lý sợ bị đánh giá khi nói chuyện với giáo viên người thật.
  - *Từ chính điểm nghẽn của Speak:* Tín hiệu review 1-sao thực tế phản ánh học viên ức chế khi hệ thống nhận diện quá khắt khe ở âm tiết ngắn (như từ *"how's"* đọc cả chục lần vẫn báo sai) hoặc nội dung nâng cao bị lặp lại.
- **2. PULL (Lực kéo):** Trải nghiệm độc quyền nói thành tiếng 20–30 câu/bài trong không gian an toàn; phản hồi sửa ngữ pháp thời gian thực; tính năng gia sư AI Live tương tác song công ngắt lời tự nhiên như người thật.
- **3. ANXIETY (Sự lo ngại):**
  - *Khi bắt đầu:* Nỗi sợ bị trừ tiền tự động sau kỳ dùng thử (Review 04/01/2026: bị trừ 1.443.333 VNĐ thay vì 1.299.000 VNĐ niêm yết; quy trình hủy trial phức tạp).
  - *Khi rời đi:* Tiếc dữ liệu tích lũy và thước đo năng lực "Speak Level"; lo ngại các công cụ miễn phí như ChatGPT Voice không có giáo trình sư phạm dẫn dắt.
- **4. HABIT (Thói quen & Switching Cost):**
  - *Ở mảng B2C:* Thói quen duy trì tương đối yếu; người dùng chỉ thấy đáng tiền ở tháng luyện tập cao điểm, sau đó dễ bỏ cuộc (dẫn đến việc Speak phải gấp rút bổ sung Streak Freeze cuối 2025).
  - *Ở mảng B2B:* Switching cost cực cao vì gắn với ngân sách đào tạo của công ty, dashboard theo dõi của phòng L&D và KPI của nhân viên.

---

## §3. Ba dự đoán hướng đi (6–12 tháng tới)

### Dự đoán 1 *(Loại: Mở rộng Segment / Thay đổi người trả tiền)*
- **Dự đoán:** Speak for Business (B2B) sẽ trở thành động cơ tăng trưởng doanh thu chính, mở rộng từ Hàn Quốc sang toàn bộ các chi nhánh tại Nhật Bản, Đài Loan và Mỹ, đi kèm việc nâng cấp toàn diện cổng quản trị (L&D Analytics Dashboard) để chứng minh ROI đào tạo cho doanh nghiệp.
- **Lập luận (Dẫn chứng từ §1 & §2):**
  - Dẫn từ mốc H2/2024 ở §1 và Tệp B2B ở §2: Ở B2C, rào cản Habit yếu và CAC ngày càng đắt đỏ; trong khi B2B giải quyết triệt để vấn đề này bằng hợp đồng năm có cam kết.
  - Minh chứng tuyển dụng: Speak đang tuyển vị trí *Product Lead, Enterprise* tại Tokyo và Đài Bắc để trực tiếp xây dựng roadmap cho người mua doanh nghiệp (L&D manager, admin portal, team progress reporting).
  - Khả năng bị làm sai (Falsification): Nếu sau 12 tháng, doanh thu B2B vẫn chiếm dưới 20% tổng ARR hoặc Speak cắt giảm nhân sự mảng Enterprise. Độ tự tin: **85%**.

### Dự đoán 2 *(Loại: Mở rộng tính năng / Chuẩn hóa thước đo năng lực)*
- **Dự đoán:** Speak sẽ phát triển bài kiểm tra trình độ độc lập (Placement Test & Speak Proficiency Test) và thúc đẩy để "Speak Level" trở thành chứng chỉ năng lực nói tiếng Anh được các doanh nghiệp và tổ chức tuyển dụng chấp nhận thay thế cho các bài thi nói truyền thống.
- **Lập luận (Dẫn chứng từ §1 & §2):**
  - Dẫn từ mốc Winter Release 10/12/2025 ở §1 (chuẩn hóa Speak Level) và nhu cầu đo lường ROI ở §2: Cả học viên cá nhân lẫn người quản lý L&D đều cần một thước đo tiến bộ định lượng khách quan để biện minh cho khoản chi phí bỏ ra.
  - Tương tự bài học thành công của Duolingo English Test (DET), việc sở hữu một chứng chỉ năng lực chuẩn mực sẽ tạo ra mạng lưới phòng thủ (Network Moat) và nâng Switching Cost của học viên lên mức tối đa.
  - Khả năng bị làm sai (Falsification): Nếu Speak bỏ dở hệ thống chấm điểm Speak Level và quay lại thang đo chung CEFR mà không có bài kiểm tra riêng. Độ tự tin: **75%**.

### Dự đoán 3 *(Loại: Phòng thủ trước Big Tech / Củng cố Pedagogical Moat)*
- **Dự đoán:** Speak sẽ không cạnh tranh thuần túy về độ thông minh của LLM với OpenAI hay Google, mà sẽ tập trung toàn lực vào **Pedagogical Workflow Moat** (phần mềm sư phạm chuyên sâu): cá nhân hóa sổ tay sửa lỗi (Error Notebook), tối ưu mô hình phát hiện lỗi phát âm đặc thù theo tiếng mẹ đẻ, và tinh chỉnh cơ chế can thiệp sửa sai thông minh trong lúc đàm thoại Live.
- **Lập luận (Dẫn chứng từ §1 & §2):**
  - Dẫn từ bài học "Wrapper vs. Moat" ở mốc 14/03/2023, mốc 2024 (tự train voice model) và mốc 10/9/2026 (GPT-Live): Khi công nghệ voice LLM đa dụng trở thành hàng hóa phổ thông (commodity), rào cản phòng thủ duy nhất của Speak là dữ liệu sửa lỗi sư phạm và trải nghiệm học có cấu trúc Learn -> Practice -> Apply.
  - Tín hiệu từ review 1-sao ở §2 (lỗi chấm oan ở các âm tiết ngắn như *"how's"*): Bắt buộc Speak phải hoàn thiện mô hình nhận diện giọng nói chuyên biệt cho người học ngoại ngữ, thứ mà các mô hình ASR chung như Whisper không thể giải quyết trọn vẹn.
  - Khả năng bị làm sai (Falsification): Nếu Speak dừng đầu tư vào voice model nội bộ và chuyển sang dùng 100% giải pháp voice nguyên bản của OpenAI mà không có lớp tinh chỉnh sư phạm nào. Độ tự tin: **70%**.

---

## §4. AI Log

| Việc | AI làm hay bạn làm? | Bạn kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| **1. Thu thập dữ liệu timeline & sự kiện gọi vốn của Speak** | AI hỗ trợ tra cứu sơ bộ dữ liệu từ TechCrunch, Forbes, Speak Blog | Đối chiếu từng mốc với 8 bài báo gốc và link phát hành chính thức của Speak; phát hiện và loại bỏ 2 mốc ảo AI tự suy diễn không có link kiểm chứng (như tin đồn mở lớp học VR/AR). |
| **2. Chọn lọc 8 cột mốc đưa vào memo** | **Bạn làm** (định hướng tiêu chí quyết định sản phẩm chiến lược) | Tự cân nhắc và kiên quyết loại bỏ các mốc không đủ chuẩn chiến lược như: các bản cập nhật giao diện (UI/Dark mode), các chiến dịch marketing giảm giá mùa tựu trường, và các bản vá lỗi kỹ thuật thường nhật. |
| **3. Phân tích chân dung người dùng & cấu trúc 4 Forces (JTBD)** | AI phác thảo khung lý thuyết 4 Forces ban đầu | Bác bỏ nhận định lý thuyết màu hồng của AI; trực tiếp tìm kiếm và đưa vào các tín hiệu review 1–2 sao thực tế trên App Store / Google Play (sự cố trừ tiền trial 1.443.333 VNĐ, lỗi nhận diện từ *"how's"*), chỉ rõ điểm yếu Habit của B2C. |
| **4. Xây dựng 3 dự đoán chiến lược 6–12 tháng tới** | Phối hợp: Bạn định hình 3 bài toán then chốt (B2B, Khảo thí Speak Level, Moat sư phạm); AI hỗ trợ cấu trúc hóa lập luận | Tự truy cập trang tuyển dụng Wellfound và trang Careers của Speak để kiểm chứng việc Speak đang tuyển *Product Lead Enterprise* tại Nhật và Đài Loan, từ đó ấn định độ tự tin dự đoán B2B đạt 85%. |
| **5. Định dạng, biên tập và chuẩn hóa cấu trúc memo** | AI hỗ trợ chuyển đổi bảng Markdown và vẽ sơ đồ Mermaid | Tự rà soát toàn bộ các câu hỏi phản biện của từng Checkpoint, đảm bảo tính liên kết logic chặt chẽ giữa dữ liệu §1, động lực §2 và dự đoán §3. |

---

### Trả lời câu hỏi phản biện Checkpoint CP4:
> **❓ Câu hỏi:** *Chỗ nào trong bài AI làm thay nhiều nhất? Nếu bỏ phần đó ra, bạn còn tự giải thích được không?*
>
> **💡 Trả lời:**
> - **Phần AI làm thay nhiều nhất:** Là việc tổng hợp và định dạng văn bản chi tiết cho 8 hàng của bảng Timeline (§1) cùng với việc dựng khung lý thuyết ban đầu cho mô hình 4 Forces (§2).
> - **Nếu bỏ phần đó ra, tôi hoàn toàn tự giải thích được:** Bởi vì toàn bộ khung lập luận cốt lõi của bài viết được xây dựng dựa trên 3 nguyên lý mà chính tôi đã lựa chọn và kiểm chứng:
>   1. *Bản chất của Moat trong kỷ nguyên AI:* AI model nền tảng (LLM/Voice) là tài nguyên đi thuê; moat thực sự của Speak nằm ở **data flywheel phát âm lỗi** và **workflow sư phạm bài bản** (Learn -> Practice -> Apply).
>   2. *Động lực chuyển dịch kinh doanh:* B2C bị nghẽn bởi chi phí CAC và thói quen lỏng lẻo; việc Speak chuyển sang B2B Enterprise là nước cờ bắt buộc để xây dựng switching cost tổ chức bền vững.
>   3. *Bằng chứng từ thực tế:* Các điểm nghẽn về ma sát thanh toán trial và lỗi chấm âm tiết ngắn từ review 1-sao là cơ sở thực chứng vững chắc nhất để dự đoán bài toán sản phẩm mà đội ngũ Speak buộc phải giải quyết trong 6–12 tháng tới.
