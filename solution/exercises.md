# K4 — Ngày 1: Bài Tập & Phản Ánh
## Khám Phá LLM API | Phiếu Thực Hành

**Thời lượng:** 4 tiếng
**Cách làm:** Trả lời từng câu ngay sau khi hoàn thành block tương ứng —
đừng để dồn hết về cuối buổi. Thay dòng `*Câu trả lời của bạn*` bằng câu
trả lời thật (chấm tự động sẽ đếm số câu đã trả lời).

---

## Block 1 — API Cơ Bản (trả lời sau Checkpoint 1)

### Câu 1.1 — Độ nhạy của temperature
Gọi `call_openai` với temperature 0.0, 0.5, 1.0 và 1.5 dùng prompt
**"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**
0.0: ('Một sự thật thú vị về Việt Nam là đất nước này có một hệ thống hang động lớn nhất thế giới, đó là hang Sơn Đoòng. Hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình. Hang động này được phát hiện vào năm 1991 bởi một người dân địa phương tên là Hồ Khanh, nhưng mãi đến năm 2009, một đoàn thám hiểm người Anh mới chính thức khảo sát và công bố về kích thước khổng lồ của nó. Hang Sơn Đoòng có chiều dài hơn 5 km, cao 200 m và rộng 150 m, đủ lớn để chứa cả một tòa nhà chọc trời 40 tầng. Bên trong hang có cả một hệ sinh thái riêng với rừng cây, sông ngầm và các loài động thực vật độc đáo.', 4.7673069000002215)

0.5:  ('Một sự thật thú vị về Việt Nam là đất nước này có hệ thống hang động lớn nhất thế giới, đó là hang Sơn Đoòng. Nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng ở tỉnh Quảng Bình, hang Sơn Đoòng được phát hiện vào năm 1991 bởi một người dân địa phương và được công nhận là hang động lớn nhất thế giới vào năm 2009. Hang có chiều dài khoảng 9 km, với các khoang lớn có thể chứa được cả một tòa nhà chọc trời 40 tầng. Bên trong hang còn có cả hệ sinh thái riêng với rừng nguyên sinh, sông ngầm và những đám mây mù. Đây là một điểm đến hấp dẫn cho những người yêu thích khám phá và phiêu lưu.', 3.2806988000002093)

1.0: ('Một sự thật thú vị về Việt Nam là nước này có hang động tự nhiên lớn nhất thế giới, đó là hang Sơn Đoòng. Nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng ở tỉnh Quảng Bình, hang Sơn Đoòng có chiều dài hơn 5 km, cao 200 m và rộng 150 m. Hang động này có cả một hệ sinh thái riêng với sông ngầm, rừng cây và thậm chí là các đám mây riêng. Sơn Đoòng được khám phá lần đầu tiên vào năm 1991 bởi một người dân địa phương, nhưng mãi đến năm 2009, hang động mới được các nhà thám hiểm quốc tế công nhận rộng rãi.', 2.8647890000002008)

1.5:  ('Một sự thật thú vị về Việt Nam là quốc gia này có hệ thống hang động lớn nhất thế giới, được biết đến với tên gọi Hang Sơn Đoòng. Nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng ở tỉnh Quảng Bình, Hang Sơn Đoòng được phát hiện vào năm 1991 bởi một người dân địa phương và được khảo sát kỹ lưỡng vào năm 2009 bởi một nhóm thám hiểm người Anh. Hang có một hệ sinh thái riêng với rừng cây, sông ngầm và các loài động thực vật đặc hữu. Một số đoạn của hang lớn đến mức có thể chứa một tòa nhà chọc trời 40 tầng. Sơn Đoòng đã thu hút sự chú ý của giới khoa học và du khách trên toàn thế giới, trở thành một điểm đến mơ ước cho những người đam mê khám phá và yêu thiên nhiên.', 3.7795556999999462)

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> *Câu trả lời của bạn*
Khi temperature tăng dần từ 0.0 đến 1.5, văn bản có sự biến đổi linh hoạt về từ vựng và cách diễn đạt: ở mức 0.0, câu trả lời mang tính cố định và chi tiết nhất, trong khi các mức cao hơn tạo ra các biến thể khác nhau về câu chữ nhưng vẫn giữ nguyên ý chính. Tuy nhiên, thời gian phản hồi (latency) lại không tuân theo một quy luật tuyến tính nào dựa trên mức nhiệt độ mà dao động ngẫu nhiên tùy thuộc vào thời điểm gọi API.

### Câu 1.2 — Chọn temperature cho sản phẩm
**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> *Câu trả lời của bạn*
Khoảng từ 0.0 đến 0.3 để đảm bảo tính chính xác và nhất quán vì hỗ trợ khách hàng đòi hỏi thông tin về chính sách, giá cả, hướng dẫn sử dụng hoặc phải cực kỳ chính xác. Đồng thời đảm bảo tính chuyên nghiệp, được câu trả lời rõ ràng, trực trọng tâm và đáng tin cậy, thay vì những câu văn, văn hoa hay thay đổi cách trả lời liên tục cho cùng một câu hỏi. Không chọn hoàn toàn 0.0 để không quá máy móc, cứng nhắc, tạo tính uyển chuyển, tự nhiên.

### Câu 1.3 — Đánh đổi chi phí
Kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người gọi API 3 lần,
mỗi lần trung bình ~350 token đầu ra.

**Ước tính GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này? Nêu một
trường hợp GPT-4o xứng đáng với chi phí và một trường hợp nên dùng mini:**
> *Câu trả lời của bạn*
GPT-4o: $10.00 chuyên cho mỗi 1 triệu token (tương đương $0.010 cho mỗi 1K token).
GPT-4o-mini: $0.60 cho mỗi 1 triệu token (tương đương $0.0006 cho mỗi 1K token).
=> Chi phí của GPT-4o đắt hơn GPT-4o-mini khoảng 16.67 lần

Trường hợp GPT-4o xứng đáng với chi phí: Khi gặp tác vụ khó, phức tạp như phân tích thuật toán, coding, dịch thuật cấu trúc dữ liệu nhiều tầng đòi hỏi tư duy logic. Hoặc khi phân tích tài liệu chuyên sâu, đa ngôn ngữ học thuật, khi cần phân tích ngữ nghĩa phức tạp, sáng tạo văn bản nghệ thuật cấp cao hoặc xử lý các yêu cầu ngặt nghèo.

Trường hợp GPT-4o-mini xứng đáng với chi phí: Khi chăm sóc khách hàng tự động, trả lời các câu hỏi thường gặp, hướng dẫn thủ tục, kiểm tra các vấn đề cơ bản, những tác vụ cần tốc độ và số lượng thay vì tư duy. Hoặc khi cần tóm tắt văn bản, trích xuất dữ liệu thô.
---

## Block 2 — System Prompt & Token (trả lời sau Checkpoint 2)

### Câu 2.1 — Sức mạnh của persona
Gọi `chat_with_system_prompt` hai lần với cùng câu hỏi
**"Giải thích blockchain là gì?"** nhưng hai system prompt khác nhau:
- "Bạn là giáo viên tiểu học, giải thích thật đơn giản cho trẻ 8 tuổi."
- "Bạn là chuyên gia tài chính, trả lời chuyên sâu bằng thuật ngữ kỹ thuật."

**Hai phản hồi khác nhau như thế nào (độ dài, từ vựng, ví dụ)? System prompt
ảnh hưởng đến hành vi model ra sao?** (3–4 câu)

system prompt 1: ('Blockchain giống như một cuốn sổ tay đặc biệt mà rất nhiều người có thể cùng viết vào, nhưng không ai có thể xóa hay sửa những gì đã ghi. Mỗi trang trong cuốn sổ đó gọi là một "khối" và khi viết đầy một trang, chúng ta sẽ chuyển sang trang tiếp theo, gắn liền với trang trước đó. Điều này tạo nên một "chuỗi" các trang, hay còn gọi là "chuỗi khối" (blockchain). \n\nĐiều thú vị là cuốn sổ này được lưu giữ trên rất nhiều máy tính khác nhau, nên ai cũng có thể kiểm tra và đảm bảo rằng không có gì bị thay đổi. Blockchain thường được dùng để ghi lại thông tin một cách an toàn và minh bạch, như khi trao đổi tiền điện tử.', 3.5827707999997074)

system prompt 2: ('Blockchain là một công nghệ sổ cái phân tán (Distributed Ledger Technology - DLT) cho phép lưu trữ thông tin một cách minh bạch và bất biến. Nó hoạt động như một cơ sở dữ liệu phi tập trung, nơi dữ liệu được ghi lại trong các khối (block) và mỗi khối chứa thông tin về một giao dịch hoặc nhiều giao dịch. Các khối này được liên kết với nhau theo thứ tự thời gian thành một chuỗi, vì vậy gọi là "blockchain" (chuỗi khối).\n\nMột số đặc điểm kỹ thuật nổi bật của blockchain bao gồm:\n\n1. **Phi tập trung (Decentralization):** Không có cơ quan trung ương kiểm soát dữ liệu. Thay vào đó, dữ liệu được phân phối trên nhiều nút mạng (nodes), mỗi nút giữ một bản sao của toàn bộ sổ cái.\n\n2. **Bất biến (Immutability):** Một khi dữ liệu đã được ghi vào blockchain, nó gần như không thể bị thay đổi hoặc xóa bỏ, nhờ vào việc sử dụng các hàm băm mật mã (cryptographic hashing).\n\n3. **Minh bạch (Transparency):** Tất cả các giao dịch đều có thể được kiểm tra', 3.82298499999888)

> *Câu trả lời của bạn*
Phản hồi thứ nhất sử dụng từ ngữ bình dân, hình ảnh ví dụ trực quan như "cuốn sổ tay" để trẻ em dễ hiểu, trong khi phản hồi thứ hai dùng từ vựng chuyên ngành phức tạp như "sổ cái phân tán", "bất biến" và "hàm băm mật mã". Về cấu trúc, câu trả lời của giáo viên ngắn gọn, liền mạch dạng kể chuyện, còn câu trả lời của chuyên gia dài hơn và được phân chia thành các luận điểm kỹ thuật rõ ràng. Qua đó, system prompt đóng vai trò định hướng "nhân vật" (persona), chi phối hoàn toàn giọng điệu, tầng kiến thức và cách mô hình gói gọn thông tin để đáp ứng đúng đối tượng mục tiêu.

### Câu 2.2 — tiktoken vs đếm từ
Chọn một đoạn văn tiếng Việt ~100 từ. So sánh số token theo `count_tokens`
(tiktoken) với ước lượng `số từ / 0.75` mà Part 1 đã dùng.

**Hai con số chênh nhau bao nhiêu phần trăm? Vì sao tiếng Việt thường tốn
nhiều token hơn tiếng Anh cùng độ dài?**
> *Câu trả lời của bạn*
Ước lượng `số từ / 0.75` ở Part 1: 100 / 0.75 = 133 token
Đếm bằng hàm `count_tokens` ~ 212 token
=> Hai con số chênh nhau khoảng 59.4%.

Tiếng Việt tốn token hơn tiếng Anh vì tiktoken được huấn luyện chủ yếu trên kho ngữ liệu tiếng Anh và các ngôn ngữ phổ biến Tây Âu. Do đó, các từ/âm tiết tiếng Anh thường chiếm trọn 1 token, trong khi tiếng Việt ít có sẵn các cụm từ nguyên khối trong bảng mã. Tiếng Việt có rất nhiều dấu (sắc, huyền, hỏi, ngã, nặng) và các nguyên âm có dấu (â, ê, ô, ư, đ). Khi bộ mã hóa không nhận diện được trọn vẹn một từ có dấu phức tạp, nó sẽ bẻ nhỏ từ đó ra thành nhiều mảnh (sub-tokens hoặc byte nhỏ hơn), khiến số lượng token tăng lên đáng kể.
---

## Block 3 — Streaming & Độ Bền (trả lời sau Checkpoint 3)

### Câu 3.1 — Trải nghiệm người dùng với streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì
non-streaming lại phù hợp hơn?** (1 đoạn văn)
> *Câu trả lời của bạn*
Streaming đóng vai trò quan trọng nhất trong các ứng dụng tương tác trực tiếp (như chatbot) hoặc khi sinh ra các đoạn văn bản dài, giúp giảm đáng kể độ trễ cảm nhận và mang lại trải nghiệm mượt mà, phản hồi ngay lập tức cho người dùng thay vì phải chờ đợi toàn bộ câu trả lời hoàn tất. Ngược lại, chế độ non-streaming lại phù hợp hơn trong các tác vụ lập trình tự động hóa (API-to-API), xử lý dữ liệu cấu trúc (như yêu cầu model trả về định dạng JSON) hoặc các hệ thống hạ lưu bắt buộc phải nhận trọn vẹn toàn bộ nội dung một lần để kiểm tra tính hợp lệ và phân tích cú pháp trước khi thực hiện bước tiếp theo.

### Câu 3.2 — Vì sao backoff theo cấp số nhân?
**So với delay cố định (ví dụ luôn chờ 1 giây), exponential backoff có lợi
thế gì khi API bị quá tải? Điều gì xảy ra nếu hàng nghìn client cùng retry
với delay cố định giống nhau?**
> *Câu trả lời của bạn*
- Exponential backoff tăng thời gian chờ sau mỗi lần thử thất bại theo lũy thừa của 2. Cách này giúp hệ thống tự động thích ứng: vừa thử lại nhanh ở các lần đầu (phòng khi lỗi mạng chớp nhoáng), vừa giãn rộng khoảng thời gian chờ ra xa hơn ở các lần sau nếu lỗi kéo dài, tránh việc dồn dập gửi request làm trầm trọng thêm tình trạng quá tải của máy chủ.

- Nếu hàng nghìn client cùng gặp lỗi và được lập trình chờ một khoảng thời gian cố định (ví dụ 1 giây), chúng đồng loạt gửi lại request vào cùng một thời điểm sau 1 giây đó. Tạo ra một đợt sóng truy cập đột biến, khiến máy chủ vừa chớm hồi phục lại tiếp tục bị đánh sập ngay lập tức. 
---

## Block 4 — Mini-Project (trả lời sau Checkpoint 4)

### Câu 4.1 — Thiết kế persona
**Bạn chọn persona gì cho trợ lý của mình? Viết lại system prompt đó và giải
thích 1–2 lựa chọn từ ngữ quan trọng trong prompt (ví dụ: vì sao yêu cầu
"trả lời ngắn gọn", vì sao chỉ định ngôn ngữ...):**
> *Câu trả lời của bạn*
"giảng viên khoa học AI uyên bác, chuyên phân tích bản chất công nghệ": Định hình rõ tư duy và tầng kiến thức của mô hình, giúp câu trả lời không bị hời hợt hay giải thích chung chung, mà hướng đến việc cung cấp góc nhìn chuyên môn, phân tích sâu về bản chất kỹ thuật thay vì chỉ nêu bề nổi.

"liệt kê các ý thành đầu dòng": Ép cấu trúc đầu ra phải được trình bày theo dạng phân cấp (bullet points). Điều này giúp người đọc dễ dàng quét qua các ý chính, cấu trúc hóa lượng thông tin học thuật lớn một cách mạch lạc và không bị rối mắt.

### Câu 4.2 — Hạn chế & cải thiện
**Trợ lý của bạn hiện có hạn chế lớn nhất là gì (ví dụ: history chỉ 3 lượt,
không có bộ nhớ dài hạn, không kiểm duyệt nội dung...)? Đề xuất một cải
thiện cụ thể và mô tả ngắn cách triển khai:**
> *Câu trả lời của bạn*
History chỉ 3 lượt hội thoại gần nhất.
Đề xuất cải tiến: Lưu trữ lịch sử hội thoại, gom chúng lại và đưa 1 mô hình nhỏ như GPT-4o-mini tóm tắt ý chính. Sau đó lưu vào vector database, chuyển các đoạn tóm tắt này thành các embedding và lưu. Sau mỗi câu hỏi người dùng, quét qua vector DataBase để tìm kiếm ngữ cảnh, ký ức liên quan giúp nhớ lại thông tin cũ. 
---

## Danh Sách Kiểm Tra Nộp Bài

- [ ] `python grade.py` — xem điểm tự động, mục tiêu ≥ 75/100
- [ ] Cả 4 checkpoint pytest đều pass
- [ ] Tất cả 9 câu trong file này đã được trả lời
- [ ] Đã copy bài làm vào folder `solution/`, push lên fork và dán link trên trang bài Lab ở VLearn trước 23:59 ngày 11/09/2026
