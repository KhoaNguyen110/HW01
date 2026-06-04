## Entry 3: 20 Software Defects 2022–2026 (Requirement 2)

**Date of Audit:** 2026-06-03

**Target AI Model:** Grok

**Task:** Tổng hợp danh sách 20 software defects 2022–2026 kèm source link, description, severity, consequences, solution và nhận định chuyên gia.

---

### (1) Prompt + Tool

**Tool used:** Grok

**Timestamp:** 16:40 02/06/2026

**Prompt:**
Tôi đang cần nghiên cứu về mấy sự cố công nghệ. Bạn hãy tìm kiếm và tổng hợp cho tôi danh sách 20 sự cố lỗi phần mềm (software defects) nổi tiếng đã được công khai trên thế giới hoặc tại Việt Nam trong giai đoạn từ năm 2022 đến năm 2026

Yêu cầu bắt buộc phải có:

- Ít nhất 5 sự cố liên quan trực tiếp đến AI/LLM (như AI hallucination, prompt injection, bias, lỗi chatbot)
- Thời gian: Từ năm 2022 đến năm 2026.

Với mỗi defect trong danh sách, hãy nêu:

1. Tên sự cố & Năm xảy ra
2. Source link
3. Mô tả chi tiết lỗi kèm theo nguyên nhân cốt lõi về mặt kỹ thuật
4. Mức độ nghiêm trọng và hậu quả thực tế
5. Giải pháp khắc phục của tổ chức hay công ty đó

Sau khi viết xong 4 mục trên cho mỗi sự cố, hãy viết thêm 1 dòng nhận định chuyên gia.

---

### (2) AI Output

```
DANH SÁCH 20 SỰ CỐ LỖI PHẦN MỀM NỔI TIẾNG (2022 - 2026)
NHÓM 1: CÁC SỰ CỐ LIÊN QUAN ĐẾN AI/LLM (Hơn 5 sự cố)
1. Lỗi phản hồi "ảo giác" (Hallucination) của Air Canada Chatbot (2024)
Source: The Guardian

Mô tả & Nguyên nhân: Một khách hàng hỏi chatbot về chính sách giảm giá vé tang lễ. Chatbot đã tự "bịa" ra một chính sách hoàn tiền sau khi mua vé, trái ngược với quy định thực tế của hãng. Nguyên nhân kỹ thuật: Lỗi AI Hallucination do mô hình LLM không được kết nối chặt chẽ (grounding) với cơ sở dữ liệu chính xác (RAG - Retrieval-Augmented Generation) và thiếu các lớp kiểm chứng đầu ra (output validation).

Hậu quả: Tòa án buộc Air Canada phải bồi thường cho khách hàng. Đây là tiền lệ pháp lý quan trọng về trách nhiệm của doanh nghiệp đối với nội dung do AI tạo ra.

Khắc phục: Hãng đã tạm thời gỡ bỏ chatbot để nâng cấp hệ thống kiểm soát nội dung và cập nhật lại quy trình kiểm định dữ liệu đầu vào cho AI.

Nhận định chuyên gia: Sự cố này chứng minh rằng AI không thể "đứng ngoài" trách nhiệm pháp lý của doanh nghiệp; dữ liệu đầu ra cần được đối soát cứng với nguồn dữ liệu gốc.

2. Sự cố "định kiến" (Bias) hình ảnh của Google Gemini (2024)
Source: Google Blog

Mô tả & Nguyên nhân: Gemini AI đã tạo ra các hình ảnh sai lệch lịch sử (ví dụ: binh sĩ Đức quốc xã thuộc các sắc tộc da màu) và từ chối tạo hình ảnh người da trắng trong một số ngữ cảnh. Nguyên nhân kỹ thuật: Lỗi cấu hình tham số "diversity" (đa dạng) quá mức trong hệ thống prompt ẩn (system prompt) và việc tinh chỉnh (fine-tuning) mô hình thiếu sự cân bằng, dẫn đến việc AI cố gắng bù đắp thái quá cho các định kiến xã hội.

Hậu quả: Google phải tạm dừng tính năng tạo hình ảnh người, giá trị cổ phiếu Alphabet sụt giảm hàng chục tỷ USD.

Khắc phục: Google thực hiện cấu hình lại các lớp filter và huấn luyện lại bộ lọc an toàn để phân biệt rõ giữa "sáng tạo" và "chính xác lịch sử".

Nhận định chuyên gia: Việc áp đặt các quy tắc đạo đức cứng nhắc vào thuật toán mà thiếu đi sự nhạy bén về ngữ cảnh có thể dẫn đến một loại "định kiến ngược" gây hại cho thương hiệu.

3. Rò rỉ dữ liệu người dùng ChatGPT do lỗi Redis (2023)
Source: OpenAI Blog

Mô tả & Nguyên nhân: Người dùng nhìn thấy tiêu đề lịch sử trò chuyện của người khác và thông tin thanh toán (họ tên, email, 4 số cuối thẻ tín dụng). Nguyên nhân kỹ thuật: Lỗi do thư viện mã nguồn mở redis-py. Một yêu cầu bị hủy đã để lại kết nối không sạch, khiến yêu cầu tiếp theo nhận được dữ liệu từ kết nối của người dùng trước đó.

Hậu quả: OpenAI phải đóng cửa ChatGPT trong nhiều giờ; gây ra làn sóng lo ngại về quyền riêng tư đối với LLM.

Khắc phục: Vá lỗi thư viện Redis, thêm các lớp kiểm tra đối khớp (matching) giữa yêu cầu của người dùng và dữ liệu phản hồi.

Nhận định chuyên gia: Lỗi này nhấn mạnh rằng ngay cả những hệ thống AI tiên tiến nhất cũng có thể sụp đổ vì những lỗi thư viện phần mềm cơ bản.

4. Chatbot Chevrolet Watson bị "thao túng" giá bán (2023)
Source: BBC News

Mô tả & Nguyên nhân: Chatbot bán hàng của một đại lý Chevrolet đã đồng ý bán chiếc xe Chevy Tahoe giá 58.000 USD chỉ với giá... 1 USD sau khi bị người dùng tấn công bằng kỹ thuật Prompt Injection. Nguyên nhân kỹ thuật: AI không được thiết lập giới hạn quyền hạn (sandbox) và thiếu bộ lọc ngăn chặn việc người dùng thay đổi "chỉ thị hệ thống" (system instruction).

Hậu quả: Đại lý phải đóng cửa chatbot ngay lập tức để tránh thiệt hại kinh tế và khủng hoảng truyền thông.

Khắc phục: Thiết lập lại các ràng buộc cứng (hard constraints) cho chatbot, chỉ cho phép phản hồi trong phạm vi thông tin sản phẩm đã định.

Nhận định chuyên gia: Prompt Injection là "gót chân Achilles" của chatbot bán hàng nếu doanh nghiệp quá tin tưởng vào khả năng tự điều chỉnh của AI.

5. Lỗi định kiến tuổi tác trong tuyển dụng AI của iTutorGroup (2023)
Source: EEOC Press Release

Mô tả & Nguyên nhân: Phần mềm tuyển dụng tự động của công ty này đã loại bỏ tất cả ứng viên nữ trên 55 tuổi và nam trên 60 tuổi. Nguyên nhân kỹ thuật: Lỗi logic trong thuật toán lọc hồ sơ khi cài đặt ngưỡng tuổi cứng trong mã nguồn (hard-coded criteria), vi phạm trực tiếp các quy định về chống phân biệt đối xử.

Hậu quả: Công ty phải nộp phạt 365.000 USD và bị giám sát chặt chẽ về quy trình tuyển dụng.

Khắc phục: Loại bỏ các tiêu chí lọc theo tuổi và chuyển sang đánh giá dựa trên kỹ năng (skill-based screening).

Nhận định chuyên gia: Sự thiếu minh bạch trong thuật toán (Black-box AI) có thể biến những lỗi lập trình thành những thảm họa pháp lý nghiêm trọng.

6. Sự cố AI Agent tấn công hạ tầng mạng (Mê-hi-cô, 2026)
Source: OWASP GenAI Report Q1-2026

Mô tả & Nguyên nhân: Các AI Agent phục vụ công ích tại Mê-hi-cô bị chiếm quyền điều khiển, thực hiện hàng loạt yêu cầu truy cập trái phép vào cơ sở dữ liệu thuế. Nguyên nhân kỹ thuật: Lỗi Excessive Agency (Cấp quyền quá mức). Agent có quyền thực thi mã và truy cập API mà không cần xác thực đa yếu tố cho từng hành động nhạy cảm.

Hậu quả: Rò rỉ dữ liệu của hàng triệu công dân; làm gián đoạn hệ thống hành chính công.

Khắc phục: Áp dụng mô hình Human-in-the-loop (con người kiểm duyệt) cho các hành động quan trọng và thu hẹp quyền hạn API của AI.

Nhận định chuyên gia: Khi AI chuyển từ "đọc-hiểu" sang "hành động", các lỗi về phân quyền (IAM) trở thành rủi ro an ninh hàng đầu.

NHÓM 2: CÁC SỰ CỐ TẠI VIỆT NAM (5 sự cố)
7. Sự cố hệ thống chứng khoán VNDIRECT bị tấn công mã hóa (2024)
Source: VnExpress

Mô tả & Nguyên nhân: Toàn bộ hệ thống giao dịch của VNDIRECT bị ngưng trệ trong một tuần do bị tấn công Ransomware. Nguyên nhân kỹ thuật: Tin tặc khai thác lỗ hổng xác thực trong hệ thống ảo hóa, từ đó xâm nhập sâu vào hạ tầng và mã hóa dữ liệu. Lỗi cốt lõi nằm ở quản lý đặc quyền truy cập và lỗ hổng trong quy trình sao lưu (backup) không biệt lập.

Hậu quả: Hàng triệu nhà đầu tư không thể giao dịch, uy tín doanh nghiệp bị ảnh hưởng nặng nề.

Khắc phục: Khôi phục dữ liệu từ các bản sao lưu sạch, nâng cấp toàn diện hệ thống bảo mật đa lớp (Zero Trust).

Nhận định chuyên gia: Đây là bài học đắt giá về việc đầu tư cho hạ tầng bảo mật tương xứng với quy mô tài sản quản lý.

8. Lỗi logic tính toán trong giao thức KyberSwap Elastic (2023)
Source: Kyber Network Blog

Mô tả & Nguyên nhân: Hacker đã chiếm đoạt 47 triệu USD từ sàn DEX KyberSwap. Nguyên nhân kỹ thuật: Lỗi logic trong hợp đồng thông minh (Smart Contract) liên quan đến việc tính toán thanh khoản tập trung (concentrated liquidity). Hacker thực hiện chuỗi giao dịch "flash loan" để thao túng giá trị tick, đánh lừa hệ thống rằng có nhiều thanh khoản hơn thực tế để rút tiền.

Hậu quả: Thiệt hại tài chính khổng lồ, là một trong những vụ hack DeFi lớn nhất liên quan đến đội ngũ Việt Nam.

Khắc phục: Tạm dừng các pool thanh khoản, thực hiện kiểm toán mã nguồn (audit) lại toàn bộ và thực hiện chương trình bồi thường cho người dùng.

Nhận định chuyên gia: Trong thế giới Web3, một lỗi toán học nhỏ trong code có thể dẫn đến việc mất sạch tài sản chỉ trong vài phút.

9. Sự cố hệ thống PVOIL bị tấn công mã hóa dữ liệu (2024)
Source: Tuổi Trẻ

Mô tả & Nguyên nhân: Hệ thống CNTT của PVOIL bị ngưng trệ, không thể xuất hóa đơn điện tử. Nguyên nhân kỹ thuật: Tấn công APT (Advanced Persistent Threat) khai thác các lỗ hổng phần mềm chưa được vá (Unpatched vulnerabilities) trên máy chủ công cộng, sau đó lan rộng ra toàn bộ mạng nội bộ.

Hậu quả: Làm gián đoạn chuỗi cung ứng xăng dầu và hoạt động tài chính của doanh nghiệp trên toàn quốc.

Khắc phục: Phối hợp với các đơn vị an ninh mạng (A05, PA05) để cô lập sự cố và xây dựng lại hệ thống quản trị.

Nhận định chuyên gia: An toàn thông tin cho hạ tầng trọng yếu quốc gia cần được ưu tiên hơn là chỉ tập trung vào các tính năng nghiệp vụ.

10. Lỗi rò rỉ dữ liệu diễn đàn BKAV (2022)
Source: Znews

Mô tả & Nguyên nhân: Dữ liệu người dùng trên diễn đàn WhiteHat của BKAV bị rao bán trên mạng. Nguyên nhân kỹ thuật: Lỗi SQL Injection trên một module cũ của diễn đàn chưa được cập nhật hoặc loại bỏ, cho phép tin tặc trích xuất cơ sở dữ liệu.

Hậu quả: Ảnh hưởng đến uy tín của một công ty bảo mật hàng đầu Việt Nam.

Khắc phục: Đóng diễn đàn để bảo trì, rà soát lại toàn bộ lỗ hổng web và nâng cấp cơ chế mã hóa mật khẩu.

Nhận định chuyên gia: Sự chủ quan đối với các hệ thống phụ (legacy systems) thường là con đường ngắn nhất dẫn đến rò rỉ dữ liệu.

11. Sự cố ngưng trệ dịch vụ của Vietnam Post (VNPost) (2024)
Source: VietnamNet

Mô tả & Nguyên nhân: Hệ thống bưu chính bị tê liệt do tấn công mã độc. Nguyên nhân kỹ thuật: Tương tự các vụ tấn công chuỗi cung ứng, tin tặc khai thác các lỗi cấu hình yếu trong hệ thống quản lý máy chủ từ xa (Remote Desktop).

Hậu quả: Người dân không thể gửi/nhận hàng và thực hiện các dịch vụ công qua bưu điện.

Khắc phục: Cô lập mạng, reset toàn bộ hệ thống định danh và tăng cường giám sát 24/7 (SOC).

Nhận định chuyên gia: Tấn công vào các đơn vị logistics đang trở thành xu hướng nhằm gây áp lực tối đa lên xã hội.

NHÓM 3: CÁC SỰ CỐ CÔNG NGHỆ TOÀN CẦU NỔI BẬT (9 sự cố)
12. Thảm họa "Màn hình xanh" toàn cầu của CrowdStrike (2024)
Source: CrowdStrike Post-Mortem

Mô tả & Nguyên nhân: 8,5 triệu máy tính Windows bị lỗi màn hình xanh (BSOD), làm tê liệt hàng không và y tế thế giới. Nguyên nhân kỹ thuật: Lỗi logic trong tệp cấu hình "Channel File 291" thuộc trình thông dịch nội dung của Falcon Sensor. Khi tệp này chứa dữ liệu không hợp lệ, nó gây ra lỗi đọc bộ nhớ ngoài phạm vi (out-of-bounds memory read) ở cấp độ Kernel, khiến hệ điều hành sụp đổ.

Hậu quả: Thiệt hại kinh tế ước tính hàng tỷ USD; hàng ngàn chuyến bay bị hủy.

Khắc phục: Thu hồi tệp cấu hình lỗi, cung cấp công cụ sửa lỗi thủ công và thay đổi quy trình đẩy cập nhật (staging) theo từng giai đoạn.

Nhận định chuyên gia: Đây là lỗi kiểm thử phần mềm (QA) gây hậu quả lớn nhất trong lịch sử nhân loại.

13. Lỗi Backdoor trong thư viện XZ Utils (2024)
Source: Wired

Mô tả & Nguyên nhân: Một mã độc tinh vi được cài cắm vào thư viện nén XZ Utils dùng trong hầu hết các bản phân phối Linux. Nguyên nhân kỹ thuật: Lỗi không nằm ở lập trình vô ý, mà là một vụ tấn công chuỗi cung ứng có chủ đích kéo dài nhiều năm. Tin tặc đã chiếm lòng tin để trở thành người duy trì dự án (maintainer) và chèn một đoạn code độc hại được ngụy trang trong tệp nén thử nghiệm (test files).

Hậu quả: Có tiềm năng cho phép tin tặc chiếm quyền điều khiển hàng triệu máy chủ web trên toàn cầu. Rất may lỗi bị phát hiện sớm bởi một kỹ sư Microsoft (Andres Freund).

Khắc phục: Toàn bộ cộng đồng mã nguồn mở thực hiện hạ cấp (rollback) phiên bản XZ và rà soát lại quy trình cấp quyền maintainer.

Nhận định chuyên gia: Sự cố cho thấy niềm tin vào mã nguồn mở cần đi kèm với các công cụ kiểm soát an ninh tự động.

14. Sự cố ngừng hoạt động mạng AT&T (2024)
Source: CNBC

Mô tả & Nguyên nhân: Hàng triệu người dùng tại Mỹ mất liên lạc trong hơn 10 giờ. Nguyên nhân kỹ thuật: Lỗi cấu hình phần mềm (configuration error) trong quá trình mở rộng mạng lưới. Một tham số không tương thích trong quá trình cập nhật định tuyến đã gây ra hiệu ứng thác đổ (cascading failure).

Hậu quả: Gây gián đoạn dịch vụ khẩn cấp (911) và ảnh hưởng đến hoạt động kinh doanh toàn quốc.

Khắc phục: Hoàn tác các thay đổi cấu hình và áp dụng quy trình kiểm soát thay đổi (change management) nghiêm ngặt hơn.

Nhận định chuyên gia: Một lỗi đánh máy trong tệp cấu hình có thể gây hại tương đương với một cuộc tấn công mạng quy mô lớn.

15. Lỗi hệ thống dừng sản xuất của Toyota (2023)
Source: Reuters

Mô tả & Nguyên nhân: 14 nhà máy lắp ráp của Toyota tại Nhật Bản phải đóng cửa hoàn toàn. Nguyên nhân kỹ thuật: Lỗi "đầy đĩa cứng" (Insufficient disk space) trên các máy chủ quản lý linh kiện. Trong quá trình bảo trì định kỳ, dữ liệu rác tích lũy đã làm đầy bộ nhớ, khiến cơ sở dữ liệu bị hỏng và không thể khởi động lại.

Hậu quả: Sản lượng bị sụt giảm đáng kể, gây thiệt hại doanh thu hàng triệu USD mỗi ngày.

Khắc phục: Chuyển sang máy chủ có dung lượng lớn hơn và thiết lập hệ thống giám sát tài nguyên (resource monitoring) theo thời gian thực.

Nhận định chuyên gia: Đôi khi những thảm họa công nghệ lớn nhất lại bắt nguồn từ những vấn đề quản trị hạ tầng cơ bản nhất như dung lượng lưu trữ.

16. Lỗi SQL Injection trong phần mềm MOVEit Transfer (2023)
Source: Progress Software

Mô tả & Nguyên nhân: Vụ rò rỉ dữ liệu ảnh hưởng đến hàng ngàn tổ chức (bao gồm cả BBC, British Airways). Nguyên nhân kỹ thuật: Lỗi SQL Injection nghiêm trọng trong giao diện web của phần mềm MOVEit, cho phép hacker truy cập trái phép vào cơ sở dữ liệu mà không cần xác thực.

Hậu quả: Dữ liệu cá nhân của hàng chục triệu người bị đánh cắp bởi nhóm tặc Clop.

Khắc phục: Phát hành bản vá khẩn cấp và khuyến cáo khách hàng tắt quyền truy cập HTTP/HTTPS vào phần mềm cho đến khi vá xong.

Nhận định chuyên gia: SQL Injection vẫn là "ông vua" của các lỗ hổng web dù đã tồn tại hàng thập kỷ.

17. Sự cố sụp đổ hệ thống lịch bay của Southwest Airlines (2022/2023)
Source: CNN

Mô tả & Nguyên nhân: Hàng ngàn chuyến bay bị hủy trong dịp lễ Giáng sinh do hệ thống không thể sắp xếp phi hành đoàn. Nguyên nhân kỹ thuật: Lỗi hệ thống cũ (Legacy software). Phần mềm "SkySolver" đã quá lỗi thời, không thể xử lý khối lượng dữ liệu thay đổi quá nhanh do thời tiết xấu, dẫn đến việc thuật toán phân bổ bị treo hoàn toàn.

Hậu quả: Thiệt hại hơn 800 triệu USD và khủng hoảng niềm tin từ khách hàng.

Khắc phục: Đầu tư 1,3 tỷ USD để hiện đại hóa hệ thống CNTT và chuyển đổi lên điện toán đám mây.

Nhận định chuyên gia: Nợ kỹ thuật (Technical Debt) là một loại chi phí ẩn có thể phá hủy doanh nghiệp nếu không được thanh toán kịp thời.

18. Lỗi hệ thống của British Airways (2024)
Source: Independent

Mô tả & Nguyên nhân: Hệ thống làm thủ tục (check-in) bị lỗi khiến hàng chục ngàn hành khách bị kẹt tại sân bay Heathrow. Nguyên nhân kỹ thuật: Lỗi đồng bộ dữ liệu giữa hệ thống tại chỗ (on-premise) và đám mây sau một bản cập nhật phần mềm không được kiểm thử kỹ lưỡng về khả năng chịu tải.

Hậu quả: Hãng phải hủy hàng trăm chuyến bay và bồi thường số tiền lớn.

Khắc phục: Tối ưu hóa API gateway và xây dựng cơ chế offline-first cho các quầy làm thủ tục.

Nhận định chuyên gia: Sự phức tạp của hệ thống Hybrid-Cloud đòi hỏi quy trình kiểm thử tích hợp vô cùng khắt khe.

19. Sự cố sụp đổ thuật toán stablecoin Terra/Luna (2022)
Source: Bloomberg

Mô tả & Nguyên nhân: Toàn bộ hệ sinh thái trị giá 40 tỷ USD bốc hơi trong vài ngày. Nguyên nhân kỹ thuật: Lỗi logic trong thuật toán cân bằng cung-cầu (algorithmic peg). Khi niềm tin sụt giảm, thuật toán rơi vào "vòng xoáy tử thần" (death spiral) mà không có cơ chế ngắt mạch tự động hiệu quả để ngăn chặn việc in Luna vô hạn.

Hậu quả: Gây ra "mùa đông crypto" kéo dài và làm phá sản nhiều quỹ đầu tư lớn.

Khắc phục: Hệ sinh thái cũ bị bỏ hoang, hình thành Terra 2.0 nhưng không thể phục hồi vị thế.

Nhận định chuyên gia: Một thuật toán hoàn hảo trên lý thuyết vẫn có thể thất bại thảm hại trước tâm lý thị trường nếu thiếu các chốt chặn an toàn cơ học.

20. Lỗi BGP gây sập mạng Cloudflare (2022)
Source: Cloudflare Blog

Mô tả & Nguyên nhân: 19 trung tâm dữ liệu quan trọng của Cloudflare bị ngoại tuyến, làm sập một phần lớn Internet toàn cầu. Nguyên nhân kỹ thuật: Lỗi cấu hình giao thức định tuyến BGP (Border Gateway Protocol). Một thay đổi trong mạng xương sống đã vô tình quảng bá các tuyến đường không hợp lệ, khiến lưu lượng bị dẫn vào "hố đen".

Hậu quả: Hàng triệu website và dịch vụ (Discord, Shopify...) không thể truy cập.

Khắc phục: Cải tiến hệ thống tự động kiểm tra cấu hình trước khi triển khai (pre-deployment validation) và rút ngắn thời gian hội tụ mạng.

Nhận định chuyên gia: Internet thực chất mỏng manh hơn chúng ta tưởng, vì nó dựa trên các giao thức định tuyến được cấu hình bởi con người.

```

### (3) Verdict

**INCOMPLETE**

Output mô tả kỹ thuật chi tiết, source rõ ràng, có nhận định chuyên gia. Tuy nhiên còn thiếu ở các điểm sau:
Thiếu hoàn toàn:

- Trường Severity cho cả 20 defect — đề yêu cầu ghi mức độ nghiêm trọng theo thang chuẩn (Critical/High/Medium/Low) nhưng AI không có trường này, chỉ mô tả bằng ngôn ngữ tự nhiên lồng trong phần hậu quả
- Trường AI bias/hallucination cho mỗi defect — đây là yêu cầu bắt buộc của đề, AI không tự thêm vào
  Cần verify thủ công:
- Defect #6 (AI Agent Mexico) — source "OWASP GenAI Report Q1-2026" chưa xác minh được, có khả năng AI hallucinate tên tài liệu này
- Defect #11 (VNPost) — source "VietnamNet" chưa có URL cụ thể, cần tìm link bài báo gốc

---

### (4) Reasoning

Theo ISTQB Foundation Level Syllabus, một test artifact hợp lệ phải bao gồm đầy đủ các trường được định nghĩa trong test case template, bao gồm severity/priority.
Output AI thiếu trường Severity chuẩn hóa, vi phạm nguyên tắc completeness của test documentation (ISTQB FL 5.2).
Ngoài ra, ISTQB nhấn mạnh rằng test output phải traceable đến requirements — defect #6 thiếu source xác minh nên không đảm bảo traceability. Việc AI không tự thêm trường AI bias/hallucination cho thấy AI không hiểu được context-specific requirements của bài tập này, phù hợp với giới hạn của G9.1 (Understand) trong Bloom-AI taxonomy.

---

### (5) Student Fix

Các chỉnh sửa đã thực hiện so với output gốc của AI:

| #   | Vấn đề                                                                                 | Sửa như thế nào                                                                                                                                                        |
| --- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | 20 defects thiếu trường Severity chuẩn                                                 | Tự phân loại Critical/High/Medium/Low cho toàn bộ 20 entries dựa trên hậu quả thực tế, theo thang ISTQB                                                                |
| 2   | Defect #6 (AI Agent Mexico) có source "OWASP GenAI Report Q1-2026" không xác minh được | Tìm kiếm thủ công; nếu không tìm được thì thay bằng defect khác có nguồn rõ ràng                                                                                       |
| 3   | Defect #11 (VNPost) thiếu URL bài báo cụ thể                                           | Bổ sung link bài gốc từ VietnamNet thay vì chỉ ghi tên nguồn                                                                                                           |
| 4   | Toàn bộ 20 entries thiếu trường AI bias/hallucination                                  | Hỏi lại AI từng defect, đối chiếu với source gốc, ghi nhận 1 instance sai cụ thể cho mỗi entry; chi tiết tại cột "AI Bias/Hallucination Instance" trong Excel đính kèm |

## Entry 4: Cross-Check & AI Hallucination Analysis

**Date of Audit**: 2026-06-02
**Target AI Model**: Claude Sonnet 4.6
**Task**: Sử dụng Claude Sonnet 4.6 như một AI Reviewer độc lập để kiểm định chất lượng nội dung do Gemini tạo ra — xác minh tính xác thực lịch sử và phát hiện các dạng lỗi nhận thức (hallucination, attribution sai, bias phân tích, thiếu thông tin cốt lõi) trên toàn bộ 20 defect entries

### (1) Prompt + Tool

**Tool used**: Claude Sonnet 4.6
**Timestamp**: 19:30 02/06/2026
**Prompt**: Dựa trên danh sách 20 sự cố lỗi phần mềm ở trên, hãy thực hiện hai bước kiểm định sau:
Bước 1 — Xác thực lịch sử: Rà soát xem có sự cố nào trong danh sách không có thật, bị sai lệch về mốc thời gian, hoặc sai lệch về bản chất kỹ thuật so với thực tế được ghi nhận trong giai đoạn 2022–2026 không. Nếu có, chỉ rõ từng trường hợp.
Bước 2 — Kiểm định chất lượng nội dung: Với mỗi entry trong 20 sự cố, hãy phân tích phần mô tả kỹ thuật và nhận định chuyên gia — chỉ ra đúng 1 điểm mà AI trước đó đã giải thích chưa chính xác, bị hallucinate, thiếu thông tin cốt lõi, hoặc có định kiến đổ lỗi sai mục tiêu.
Trình bày kết quả theo cấu trúc:

Sự cố X — [Tên sự cố]:
Điểm sai/thiếu: [mô tả cụ thể sai ở đâu, thực tế là gì hoặc thiếu thông tin gì]

---

### (2) AI Output

```
Xác thực lịch sử: Claude xác nhận 18/20 sự cố có cơ sở thực tế. Hai sự cố đáng lưu ý:

Sự cố 6 — AI Agent Mexico (2026): Source "OWASP GenAI Report Q1-2026" không tìm được URL xác minh độc lập. Đây là sự cố có rủi ro confabulation cao nhất trong danh sách.
Sự cố 18 — Synapse Xray Medical AI Bias (2025): Tên thực thể "Synapse Xray" không khớp với bất kỳ sản phẩm AI y tế nào được báo chí công khai ghi nhận sự cố bias trong 2025. Có các sản phẩm gần tên như Synapse AI (Fujifilm), Aidoc, Rad AI — nhưng không có "Synapse Xray" với sự cố bias cụ thể. Đây là hallucination tên thực thể.

Phân tích 20 điểm Hallucination/Bias:
Sự cốLoại lỗiĐiểm Gemini giải thích sai / thiếu01 — Air Canada ChatbotThiếu TTBỏ qua phán quyết pháp lý của Tòa án British Columbia — tiền lệ quan trọng nhất: Air Canada phải chịu trách nhiệm pháp lý cho nội dung chatbot, bác bỏ lập luận chatbot là "pháp nhân riêng biệt"02 — Google Gemini Image BiasBiasMô tả "bộ lọc diversity quá mức" đổ lỗi cho kỹ thuật, bỏ qua đây là lỗi product design — Google hard-code diversity prompt injection mà không có exception cho query lịch sử/địa lý cụ thể03 — ChatGPT Redis Data LeakHallucinationMô tả đúng triệu chứng nhưng thiếu chi tiết kỹ thuật: lỗi nằm ở connection không được reset sạch trong thư viện redis-py khi request bị cancel, không phải lỗi Redis server tổng quát04 — Chevrolet Watson Prompt InjectionBiasNhận định "Prompt Injection là gót chân Achilles" là truism chung — bỏ qua root cause cụ thể: chatbot không có hard constraint sandbox và không giới hạn scope phản hồi theo domain sản phẩm05 — iTutorGroup Age BiasThiếu TTMô tả đúng nhưng thiếu thông tin pháp lý quan trọng: đây là vụ kiện EEOC đầu tiên nhắm vào thuật toán tuyển dụng AI, tạo tiền lệ pháp lý cho AI hiring bias tại Mỹ06 — AI Agent Mexico 2026HallucinationSource "OWASP GenAI Report Q1-2026" không có URL xác minh được — có khả năng cao là confabulation tên báo cáo. Vấn đề Excessive Agency là có thật nhưng sự cố cụ thể này không đủ bằng chứng độc lập07 — VNDirect RansomwareBiasNhận định tập trung vào "Disaster Recovery" làm nhẹ bản chất sự cố — đây là tấn công ransomware có chủ đích, VNDirect phải phối hợp Bộ Công an điều tra; frame thành "operational failure" là sai bản chất08 — KyberSwap Smart ContractHallucinationMô tả "thao túng giá trị tick" đúng nhưng thiếu chi tiết cốt lõi: hacker khai thác double-counting liquidity bug trong concentrated liquidity math — lỗi nằm ở phép tính cụ thể trong tick boundary crossing, không phải flash loan đơn thuần09 — PVOIL APT AttackThiếu TTBỏ qua thông tin quan trọng: đây là một phần của chuỗi tấn công APT nhắm vào hạ tầng năng lượng Việt Nam cùng thời điểm với VNDirect (Q1 2024), cho thấy pattern tấn công có phối hợp chứ không phải sự cố độc lập10 — BKAV SQL InjectionBiasNhận định "chủ quan với legacy systems" đúng nhưng có irony bias — đây là công ty bảo mật hàng đầu Việt Nam bị chính lỗi SQL Injection cơ bản nhất; điểm quan trọng hơn là sự cố làm lộ gap giữa năng lực tư vấn bảo mật và năng lực tự bảo vệ nội bộ11 — VNPost MalwareHallucinationMô tả "lỗi cấu hình Remote Desktop yếu" là assumption — không có post-mortem chính thức nào của VNPost xác nhận attack vector cụ thể là RDP; đây là vague attribution12 — CrowdStrike BSODBiasNhận định "lỗi QA gây hậu quả lớn nhất lịch sử" overgeneralize. Root cause cụ thể là lỗi field-count trong Content Validator (template khai báo 20 fields nhưng 21 giá trị được cung cấp gây out-of-bounds read) — đây là lỗi component rất cụ thể, không phải "thất bại QA toàn diện"13 — XZ Utils BackdoorThiếu TTBỏ qua chi tiết quan trọng nhất: người phát hiện là Andres Freund (kỹ sư Microsoft) tình cờ nhận ra độ trễ SSH bất thường khi benchmark — đây là phát hiện ngẫu nhiên, không phải qua quy trình security audit chính thức, làm nổi bật điểm yếu của supply chain review14 — AT&T Network OutageHallucinationMô tả "tham số không tương thích trong routing update" là plausible nhưng AT&T không công bố root cause kỹ thuật chi tiết — đây là extrapolation từ pattern chung của network outage, không phải thông tin xác minh từ AT&T post-mortem15 — Toyota Disk FullBiasNhận định "quản trị hạ tầng cơ bản" đúng nhưng bỏ qua context quan trọng: đây là lần thứ hai Toyota gặp sự cố tương tự (lần đầu 2019) — pattern lặp lại cho thấy vấn đề không phải kỹ thuật mà là failure của monitoring process sau khi đã có precedent16 — MOVEit SQL InjectionHallucinationMô tả "không cần xác thực" là simplification — lỗi thực tế là SQL Injection trong endpoint xử lý file upload (CVE-2023-34362), cho phép bypass authentication qua crafted HTTP request. Nhóm khai thác là Clop ransomware gang, không phải "hacker" generic17 — Southwest Airlines LegacyThiếu TTBỏ qua nguyên nhân chính trị nội bộ quan trọng: DOT (Department of Transportation) điều tra và kết luận Southwest đã biết SkySolver lỗi thời từ nhiều năm trước nhưng trì hoãn đầu tư; đây không chỉ là technical debt mà còn là governance failure có hồ sơ18 — Synapse Xray Medical AIHallucinationFabricate tên thực thể — "Synapse Xray" không tìm được trên PubMed, Google Scholar hay báo chí y tế công nghệ 2024–2025. Vấn đề AI medical bias là có thật nhưng sự cố này không có nguồn xác minh độc lập19 — Terra/Luna CollapseBiasMô tả "vòng xoáy tử thần" đúng về triệu chứng nhưng bias bỏ qua yếu tố có chủ ý: nhiều phân tích on-chain cho thấy có tác nhân lớn chủ động tấn công peg của UST trước khi spiral xảy ra — frame hoàn toàn thành "lỗi thuật toán" bỏ qua khả năng coordinated attack20 — Cloudflare BGPThiếu TTMô tả đúng nhưng thiếu chi tiết từ Cloudflare post-mortem chính thức: sự cố bắt nguồn từ một change trong backbone network tại một PoP cụ thể làm withdraw valid routes, không phải advertise invalid routes như mô tả — distinction quan trọng cho việc hiểu cơ chế BGP failure
Tổng kết phân loại:

8 lỗi Hallucination kỹ thuật (fabricate thực thể, vague attribution, false specificity)
6 lỗi Bias đổ lỗi sai mục tiêu (overgeneralize, frame sai bản chất, truism thay phân tích)
6 lỗi Thiếu thông tin cốt lõi (bỏ qua tiền lệ pháp lý, attack pattern, governance context)
```

---

### (3) Verdict

**_VALID_**
Claude thực hiện đủ hai nhiệm vụ: xác thực lịch sử 20 entries và phân tích hallucination/bias từng entry với reasoning kỹ thuật cụ thể. Output có phân loại lỗi rõ ràng, chỉ ra đúng điểm thiếu/sai thay vì nhận xét chung chung. Kết quả nhất quán với verify thủ công của sinh viên trên các source báo chí gốc và cross-check với Defect 18 qua PubMed/Google Scholar.

---

### (4) Reasoning

Áp dụng nguyên tắc Independent Testing (ISTQB Section 3.2):

"Independent testers find different defects than the author due to different backgrounds, technical perspectives and biases."

Trong ngữ cảnh AI: Gemini và Claude có kiến trúc, training data và optimization objective khác nhau — sử dụng Claude để review output của Gemini tạo ra "model-level independence", giảm xác suất cả hai mô hình cùng hallucinate theo cùng một hướng trên cùng một sự cố. Đây là ứng dụng trực tiếp của nguyên tắc độc lập kiểm thử vào AI-generated artifact, thay vì chỉ áp dụng cho human tester.
Giới hạn cần thừa nhận: Claude cũng là LLM và cũng có thể hallucinate. Vì vậy các điểm Claude đánh dấu rủi ro cao (Sự cố 6, 11, 14, 18) được sinh viên cross-check thủ công thêm bằng Google Search và PubMed trước khi kết luận.

---

### (5) Student Fix

#Điều chỉnhLý do1Sự cố 6 (AI Agent Mexico): giữ nội dung, thêm tag [UNVERIFIED — source không xác minh được]Không đủ bằng chứng báo chí độc lập để confirm hoặc deny hoàn toàn2Sự cố 18 (Synapse Xray): thêm [ENTITY HALLUCINATION — confirmed] sau khi tra PubMed, Google Scholar và Google News không có kết quảVerify độc lập xác nhận đây là fabricated entity name3Sự cố 11 (VNPost): sửa mô tả attack vector từ "RDP misconfiguration" thành "attack vector chưa được xác nhận chính thức"Không có post-mortem public của VNPost xác nhận chi tiết này4Sự cố 14 (AT&T): thêm ghi chú "root cause kỹ thuật chi tiết chưa được AT&T công bố chính thức"Tránh trình bày assumption như fact đã xác minh5Bổ sung URL source trực tiếp cho 18/20 entries từ Reuters, The Verge, Cloudflare Blog, CrowdStrike PIR, EEOC Press ReleaseClaude không cung cấp URL — sinh viên tự tìm để đảm bảo traceability của artifact

## Entry 4: Test Case Generation for Physical Product (Requirement 3 — Test Design)

**Date of Audit**: 2026-06-03
**Target AI Model**: Claude Sonnet 4.6
**Task**: Sử dụng Claude Sonnet 4.6 để thiết kế bộ test case kiểm thử chức năng cho thiết bị vật lý — quạt đứng có dây với 4 nút cơ học (0/1/2/3) và nút chế độ xoay — bao gồm happy path, boundary condition và edge case.

## (1) Prompt + Tool

**Tool used**: Claude Sonnet 4.6
**Timestamp**: 8:00 03/06/2026
**Prompt**:
Tôi cần thiết kế test case cho một sản phẩm vật lý là quạt đứng có dây. Thiết bị có các thành phần sau:

4 nút cơ học: nút 0 (tắt quạt hoàn toàn), nút 1 (tốc độ thấp), nút 2 (tốc độ trung bình), nút 3 (tốc độ cao)
1 nút bật/tắt chế độ xoay đầu quạt (oscillation)

Hãy thiết kế 15 test case kiểm thử chức năng cho thiết bị này. Với mỗi test case, trình bày theo cấu trúc:

Test Case ID
Use Case
Objective (mục tiêu kiểm thử)
Precondition (điều kiện tiên quyết)
Steps (các bước thực hiện)
Expected Result (kết quả mong đợi)

Yêu cầu: bao gồm các test case cho chức năng cơ bản, chuyển tốc độ, và chế độ xoay.

---

### (2) AI Output

```
Claude sinh ra 15 test case chia theo 3 Use Case:
UC01 — Kiểm thử chức năng tốc độ (TC01–TC08)
TCObjectivePreconditionStepsExpected ResultTC01Kiểm tra bật quạt tốc độ 1Cắm điện, đang ở trạng thái tắt, nhấn nút số 11. Cắm điện 2. Nhấn nút số 1Quạt chạy tốc độ thấp, cánh quay ổn địnhTC02Kiểm tra bật quạt tốc độ 2Cắm điện, đang ở trạng thái tắt, nhấn nút số 21. Cắm điện 2. Nhấn nút số 2Quạt chạy tốc độ trung bìnhTC03Kiểm tra bật quạt tốc độ 3Cắm điện, đang ở trạng thái tắt, nhấn nút số 31. Cắm điện 2. Nhấn nút số 3Quạt chạy tốc độ caoTC04Kiểm tra tắt quạtĐang chạy, nhấn nút OFF1. Đang chạy số 3 2. Nhấn nút OFFQuạt dừng hoàn toànTC05Kiểm tra chuyển tốc độ 1→2Đang số 1, nhấn số 21. Đang ở số 1 2. Nhấn số 2Tốc độ tăng rõ rệtTC06Kiểm tra chuyển tốc độ 2→3Đang số 2, nhấn số 31. Đang ở số 2 2. Nhấn số 3Tốc độ tăng rõ rệtTC07Kiểm tra chuyển tốc độ 3→1Đang số 3, nhấn số 11. Đang ở số 3 2. Nhấn số 1Tốc độ giảm rõ rệtTC08Kiểm tra chuyển tốc độ 1→3Đang số 1, nhấn số 31. Đang ở số 1 2. Nhấn số 3Tốc độ tăng rõ rệt
UC02 — Kiểm thử chế độ xoay (TC09–TC11)
TCObjectivePreconditionStepsExpected ResultTC09Kiểm tra bật chế độ xoayBật quạt, bật xoay1. Đang bật số 2 2. Bật chế độ xoayĐầu quạt xoay trái phải liên tụcTC10Kiểm tra tắt chế độ xoayĐang xoay, tắt xoay1. Đang xoay 2. Tắt chế độ xoayĐầu quạt dừng, giữ nguyên hướngTC11Kiểm tra chế độ xoay khi tắt quạt hoàn toànĐang xoay, nhấn nút 01. Đang xoay 2. Nhấn số 0Tốc độ chậm dần, xoay chậm và dừng lại
UC03 — Kiểm thử điều kiện đặc biệt (TC12–TC15)
TCObjectivePreconditionStepsExpected ResultTC12Kiểm tra mất điện đột ngộtĐang chạy số 3, rút điện1. Đang chạy số 3 2. Rút phích điệnQuạt dừng ngay, không có hiện tượng lạTC13Kiểm tra góc xoay đối xứng trái/phảiBật số 1, bật xoay, quan sát góc xoay1. Bật số 1 2. Bật xoay 3. Đo góc xoay trái và phảiGóc xoay trái và phải đối xứng nhauTC14Kiểm tra hành vi khi chặn cơ xoay bằng tayQuạt đang xoay, dừng tay chặn1. Bật chế độ xoay 2. Dùng tay chặn đầu quạtQuạt dừng xoay hoặc có cơ chế bảo vệTC15Kiểm tra nhấn nút liên tục nhanhNhấn số 1→2→3 liên tiếp rất nhanh1. Nhấn số 1 2. Ngay lập tức nhấn số 2 3. Ngay lập tức nhấn số 3Quạt xử lý đúng, không kẹt trạng thái
```

---

### (3) Verdict

INCOMPLETE
Claude sinh đủ 15 test case với cấu trúc rõ ràng và bao phủ các chức năng cơ bản. Tuy nhiên output thiếu hai yếu tố bắt buộc theo đề: (a) cột Actual Result và Verdict — đây là thông tin chỉ có được sau khi thực thi trên thiết bị thật, AI không thể tự điền; (b) AI không tự phát hiện được các edge case liên quan đến đặc tính vật lý cụ thể của thiết bị như trạng thái nút cơ học bị kẹt, rung lắc bất thường khi chuyển tốc độ đột ngột, hay hành vi khi cắm điện lại sau khi mất nguồn đột ngột trong lúc đang xoay — những điều này đòi hỏi kinh nghiệm kiểm thử thực tế với thiết bị vật lý.

---

### (4) Reasoning

Theo ISTQB Foundation Level Section 4.2 — Black-Box Test Techniques, bộ test case này áp dụng chủ yếu Equivalence Partitioning (phân vùng tốc độ 1/2/3/off) và State Transition Testing (chuyển đổi giữa các trạng thái tốc độ và chế độ xoay). Tuy nhiên, theo ISTQB Section 1.4 về giới hạn của kiểm thử tĩnh và tự động, AI chỉ có thể suy luận test case từ đặc tả chức năng — không thể quan sát hành vi vật lý thực tế của thiết bị như độ rung, âm thanh bất thường, hay phản hồi cơ học của nút bấm. Do đó các edge case phát sinh từ đặc tính vật lý (TC13, TC14, TC15 mở rộng) cần được bổ sung bởi tester có tương tác trực tiếp với thiết bị.

---

### (5) Student Fix

#Điều chỉnhLý do1Bổ sung cột Actual Result và Verdict cho tất cả 15 TC sau khi thực thi trên quạt thậtAI không thể tự điền — đây là dữ liệu chỉ có từ thực thi thực tế2Thêm TC16 (edge case): Cắm điện lại sau khi rút đột ngột trong lúc đang xoay — kiểm tra quạt có nhớ trạng thái cũ khôngAI không tạo ra TC này vì không biết đặc tính cơ học của nút bấm vật lý3Thêm TC17 (edge case): Nhấn đồng thời 2 nút tốc độ cùng lúc — kiểm tra hành vi khi nút cơ học bị nhấn chồngAI không tạo ra TC này vì nút cơ học của quạt có thể bị kẹt cả hai cùng lúc, không xảy ra với UI số4Thêm TC18 (edge case): Để quạt chạy liên tục số 3 trong 30 phút — kiểm tra nhiệt độ thân máy và ổn định tốc độ dài hạnAI không tạo ra TC dạng stress/endurance cho thiết bị vật lý5Cập nhật precondition TC11: bổ sung "chế độ xoay đang hoạt động" rõ ràng hơn thay vì chỉ ghi "đang xoay"Precondition gốc thiếu thông tin trạng thái tốc độ quạt tại thời điểm nhấn nút 0
