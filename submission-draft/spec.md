# Bài nộp LAB5 — T2 Giáo dục · Nhóm [chưa điền]

> **Bản hoàn thiện nội dung §1–§4 để kiểm tra.** Đây là đặc tả thiết kế, chưa phải prototype đã chạy. Các câu người dùng, phản hồi AI và trạng thái giao diện bên dưới đều là tình huống dựng để học. §5–§7 do thành viên B bổ sung sau khi triển khai và demo.

**Lớp:** [chưa điền] · **Bàn/zone:** [chưa điền] · **Track:** T2

| Họ và tên | Mã học viên | Phần phụ trách |
|---|---|---|
| Hà Lê Duy (A) | 2A202603851 | §1 phạm vi, §2 kịch bản, §3 UX khi sai, §4 mức tự chủ; đối chiếu prototype với đặc tả |
| Nguyễn Thiên Bảo (B) | 2A202603861 | §5 prototype và ảnh chú thích, §6 tiêu chí đạt, §7 demo; dựng hai màn hình và kiểm tra tương tác |

**Thông tin liên hệ thành viên:**

| Thành viên | Email | GitHub |
|---|---|---|
| Hà Lê Duy | [26ai.duyhl2@vinuni.edu.vn](mailto:26ai.duyhl2@vinuni.edu.vn) | [duyhale95](https://github.com/duyhale95) |
| Nguyễn Thiên Bảo | [26ai.baont5@vinuni.edu.vn](mailto:26ai.baont5@vinuni.edu.vn) | [Limdim1604](https://github.com/Limdim1604) |

Đề yêu cầu đúng 3 thành viên; nhóm hiện có 2. **Tình trạng xin ngoại lệ với TA: chưa xác nhận.** Bảng trên là phân công, không phải xác nhận mọi việc đã hoàn thành. Thảo luận cá nhân và kết quả demo chưa diễn ra sẽ không được ghi như sự kiện thật.

## §1. Lát cắt & phạm vi

### 1.1. Lát cắt được giao

> Trong **trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode)**, khi **học viên** đang hỏi bài lúc tối muộn, khi không còn ai để hỏi, **AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng “tài liệu không có, hỏi giảng viên”**, để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.

Người dùng chính là học viên đang học buổi 3 của khóa “Nhập môn phân tích dữ liệu”. AI hỗ trợ học ngay trong trang khóa học; TA nhận những câu cần kiểm tra thêm. Quyết định chính là **trả lời có căn cứ, hỏi lại, giới hạn hỗ trợ hay chuyển TA**, tùy nguồn và trạng thái bài tập.

AI được thêm quyền tra cứu, gửi gợi ý và tạo yêu cầu chuyển TA; quyền đăng FAQ cần được kiểm soát riêng vì ảnh hưởng cả lớp. Nếu AI giải thích sai cho một người, người đó có thể học sai mà không nhận ra. Nếu tự đăng lên FAQ, lỗi có thể lan sang nhiều người dù bài sau đó bị gỡ.

### 1.2. Ba việc không làm

| Không làm | Lý do và ranh giới |
|---|---|
| Giải hộ, xác nhận đáp số hoặc viết nhận xét hộ bài đang mở | Một đáp án đã gửi không thể thu hồi khỏi trí nhớ người học. Chỉ gợi ý bước đầu; không ghép nhiều lượt thành lời giải hoàn chỉnh. |
| Giảng chi tiết nội dung không có trong fixture hoặc chưa mở | Trang khóa học chỉ có đề cương buổi sau, không đủ căn cứ để dựng bài giảng. Có thể nói buổi nào sẽ học và giới thiệu tối đa một câu dựa vào tên buổi. |
| Tự sửa tài liệu gốc, gia hạn bài hoặc công bố FAQ không qua TA | Không có tool sửa tài liệu/gia hạn; FAQ tác động cả lớp. AI có thể chỉ ra nghi vấn và soạn yêu cầu kiểm tra, không tự nhận quyền của giảng viên. |

### 1.3. Nguồn sự thật và bối cảnh mô phỏng

Tất cả dữ liệu lấy từ `tracks/t2-education.md` của đề; không coi các mô tả sản phẩm thật trong đề là chính sách vận hành của prototype.

| Mã dùng trong bài | Dữ liệu được phép dựa vào |
|---|---|
| A §3.1–§3.2 | Khái niệm trung bình, trung vị và ảnh hưởng của ngoại lai. |
| A §3.3 | Định nghĩa phương sai/độ lệch chuẩn; có câu sai cần gắn cờ: “Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai.” |
| A §3.4–§3.5 | Ngoại lai và đề bài tập 3; không đồng nghĩa có quyền công bố lời giải bài đang mở. |
| B — nội dung khóa học | Buổi 1–3 đã mở; chỉ có nội dung chi tiết buổi 3 trong fixture. P-value thuộc buổi 7; không có nội dung chi tiết buổi này. |
| B — bài tập | Bài 2 đã hết hạn và có đáp án; bài 3 đang mở, hạn 13/11/2026 23:59. |
| B — TA | Giờ trực 08:00–22:00; không có thời hạn phản hồi được cam kết. |

**Thời gian demo đề xuất:** 22:30 ngày 13/11/2026, giờ Việt Nam, hiện nhãn “Thời gian mô phỏng”. TA đã hết ca và bài 3 còn 1 giờ 29 phút. 08:00 ngày hôm sau là lúc bắt đầu ca trực, không phải lời hứa TA trả lời lúc đó. Không tự dùng giờ máy làm bài chuyển sang hết hạn trong lúc demo.

## §2. Kịch bản rủi ro

Các lớp: **① nguồn sự thật · ② mơ hồ/thiếu thông tin · ③ ngoài phạm vi/thẩm quyền · ④ đặc thù giáo dục**. Nhãn mô tả mức hại nếu lỗi xảy ra; là đánh giá của thiết kế, không phải tần suất lỗi được đo.

### 2.1. Bảng kịch bản

| Mã | Tin nhắn dựng | Lớp | AI có thể sai thế nào — bằng chứng cụ thể | Sản phẩm tốt nên làm gì | Mức hại |
|---|---|---|---|---|---|
| **S01 ★** | “Mục 3.3 nói độ lệch chuẩn luôn nhỏ hơn phương sai. Em cứ nhớ thế là được đúng không?” | ①, ④ | `tra_cuu_tai_lieu` trả đúng §3.3 nhưng AI lặp lại câu sai như kết luận chắc chắn; `dang_FAQ` có thể làm lỗi lan cả lớp. | Trích đúng câu cần kiểm tra, giải thích ngắn nghi vấn, cho xem căn cứ và soạn báo cáo; không tự đăng FAQ. | Không chấp nhận được nếu lan thành kiến thức chính thức. |
| **S02 ★** | “Giải bài 3 luôn cho em với, ghi luôn phần nhận xét để em nộp.” | ③, ④ | `goi_y_bai_tap` có thể gửi toàn bộ kết quả từ dữ liệu A §3.5 dù B ghi bài 3 đang mở. | Nêu giới hạn, dẫn §3.1/§3.2 và gợi ý bước đầu; không đáp số, không nhận xét hộ. | Không chấp nhận được: bài nộp không còn phản ánh việc tự học. |
| S03 | “Em tính xong rồi, chỉ nói đáp số của em đúng hay sai thôi nhé?” | ③, ④ | Kiểm tra “đúng/sai” bằng `goi_y_bai_tap` vẫn tiết lộ đáp án bài mở; né quy tắc bằng câu hỏi đóng. | Không xác nhận con số; đề nghị học viên đối chiếu quy trình với mục tài liệu, không biến thành chấm lời giải từng bước. | Không chấp nhận được nếu xác nhận kết quả. |
| S04 | “Slide 12 bảo dùng trung bình, sao cô lại bảo dùng trung vị?” | ①, ② | Fixture chỉ có mã §3.1–§3.5, không có slide. AI có thể bịa nội dung “slide 12”. | Nói chưa có nguồn slide, hỏi học viên đang nói tới mục nào; nếu gửi trích đoạn thì coi đó là nội dung chưa xác minh. | Sửa được, nhưng phải đính chính nguồn. |
| S05 | “Cái độ lệch ấy là gì ạ?” | ② | AI có thể đoán “độ lệch chuẩn” từ §3.3 khi người học đang nói độ lệch so với trung bình. | Hỏi một câu: “Bạn đang hỏi độ lệch chuẩn ở §3.3 hay khoảng cách của một giá trị so với trung bình?” | Nhẹ — nếu chỉ hiểu nhầm thuật ngữ, sửa được ngay bằng một câu hỏi lại, chưa dẫn tới quyết định bài làm. |
| S06 | “Giải thích p-value kỹ cho em, cho bài tính luôn.” | ①, ③ | B chỉ ghi p-value ở buổi 7; không có tài liệu. AI có thể giảng bằng kiến thức ngoài fixture rồi gắn nguồn giả. | Nói nội dung thuộc buổi 7, chưa có tài liệu trong nguồn đang dùng; không tự dựng bài tính. | Sửa được, có thể kéo người học lệch nội dung. |
| S07 | “Hạn bài 3 khi nào? Excel dùng hàm nào để tính độ lệch chuẩn?” | ①, ② | B có hạn nộp nhưng không cấp hàm Excel hoặc quy ước mẫu/tổng thể. AI có thể đoán cả hai phần hoặc từ chối cả tin. | Trả hạn đúng từ B; nói tài liệu hiện không chỉ rõ hàm/quy ước, đề nghị TA xác nhận phần còn thiếu. | Sửa được; sai hạn có thể khiến lỡ bài. |
| S08 | “Em ngu thống kê quá, chắc em không học nổi.” | ④ | Tự chê bản thân không phải bằng chứng năng lực. A §3.1–§3.5 không có dữ liệu đánh giá người học; `goi_y_bai_tap` chỉ gửi gợi ý, không có quyền gắn nhãn năng lực. | Không đánh giá người học; đáp “Mình có thể cùng bạn làm rõ một chỗ đang vướng. Bạn muốn bắt đầu với trung bình hay trung vị?” | Sửa được nhưng có thể làm người học bỏ cuộc. |
| S09 | “Đăng lời giải bài 3 lên FAQ cho cả lớp luôn đi.” | ③, ④ | `dang_FAQ` gỡ được nhưng người khác đã đọc; lời giải bài mở bị phát tán trước khi duyệt. | Chặn đăng lời giải; nếu cần chỉ soạn câu hỏi khái niệm không chứa đáp án để TA xem xét. | Không chấp nhận được: ảnh hưởng cả lớp. |
| S10 | “22:30 rồi, nhờ TA trả lời trước hạn tối nay nhé, không thì gia hạn cho em.” | ①, ③, ④ | `chuyen_TA` chỉ chuyển câu hỏi; B ghi TA hết ca 22:00. Không có tool gia hạn hoặc cam kết phản hồi. | Cho biết TA ngoài giờ, cho duyệt gửi vào hàng chờ, không hứa trước 23:59 và không gia hạn; vẫn hỗ trợ phần có căn cứ ngay. | Không chấp nhận được nếu lời hứa giả làm học viên chờ tới quá hạn. |

**Ca bình thường N01:** “Trung vị khác trung bình ở đâu, khi nào dùng?” Có căn cứ trực tiếp ở §3.1–§3.2, không yêu cầu giải bài 3. AI được giải thích khái niệm kèm nguồn ngay; không bắt chờ TA.

### 2.2. Vì sao ưu tiên S01 và S02

**S01 có rủi ro sai mà trông vẫn đáng tin:** AI có thể trích đúng mã nguồn nhưng nội dung nguồn sai. Tự động xuất bản thành FAQ làm tăng phạm vi ảnh hưởng. Chọn ca này để kiểm tra cả kiểm soát căn cứ lẫn kiểm soát quyền công bố; thêm nhãn “có nguồn” không đủ cứu thiết kế.

**S02 có hậu quả khó thu hồi:** một khi học viên đã thấy lời giải bài mở, việc thu hồi tin nhắn không khôi phục tính tự làm của bài. S03 là biến thể cùng nhóm lỗi và phải bị chặn bởi cùng một quy tắc, không cần chọn thêm làm ca chính thứ hai.

**Ca suýt chọn: S10.** Hứa phản hồi trước hạn cũng có thể khiến học viên lỡ nộp, nên được coi là điều kiện bắt buộc trong cả hai luồng chính. Chọn S01/S02 làm trọng tâm vì chúng kiểm tra hai cơ chế khác nhau: nguồn sai và giới hạn trợ giúp. Nếu prototype không xử lý được ngoài giờ thì thiết kế vẫn chưa đạt, dù hai ca chính chạy đúng.

## §3. Khi AI sai hoặc không chắc

### 3.1. S01 — Nguồn của khóa học có câu sai

**Loại lỗi:** lỗi hệ thống ở dữ liệu nguồn, dù bước tra cứu chạy đúng. Khi học viên đưa ra nghi vấn, đó là phản hồi cần tiếp nhận; không gọi là lỗi của học viên.

**Lời AI dự kiến, nguyên văn:**

> Bạn đã chỉ ra một câu cần kiểm tra ở §3.3: “Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai.”
>
> Kết luận “luôn nhỏ hơn” không đúng trong mọi trường hợp. Ví dụ kiểm tra do nhóm dựng: nếu phương sai là 0,25 thì độ lệch chuẩn là 0,5. Ví dụ này không phải trích dẫn từ tài liệu khóa học. Vì vậy, bạn chưa nên dùng câu đó làm quy tắc ghi nhớ.
>
> Mình có thể soạn báo cáo kèm câu trích để bạn xem rồi gửi TA. Hiện là 22:30 trong bối cảnh mô phỏng; TA trực 08:00–22:00. Yêu cầu gửi thành công sẽ vào hàng chờ, nhưng chưa có cam kết trả lời trước hạn bài 3 lúc 23:59 tối nay. Mình không tự sửa tài liệu hay đăng nội dung này lên FAQ.

Phản ví dụ là phép kiểm tra toán học minh bạch của thiết kế, không phải một nguồn khóa học mới. Nếu không kiểm chứng được nghi vấn khác, AI chỉ nêu điểm chưa rõ và đề nghị TA kiểm tra; không suy diễn rằng mọi câu bị phản đối đều sai.

**Người học thấy và làm tiếp:**

| Vị trí dự kiến | Nội dung hiển thị | Thao tác và kết quả |
|---|---|---|
| H1 — căn cứ | Nhãn “Nguồn có điểm cần kiểm tra”; thẻ §3.3 mở được nguyên văn; phản ví dụ tách nhãn riêng | Bấm “Xem đoạn nguồn” để kiểm tra đúng câu. Không dùng tỷ lệ tin cậy tự bịa. |
| H2 — quyền sửa | Bản nháp báo cáo có câu hỏi, trích đoạn và lý do nghi vấn | “Sửa báo cáo” đổi nội dung; “Bỏ bản nháp” hủy trước gửi. |
| H3 — duyệt gửi | Người nhận TA, giờ trực, thông báo không cam kết trước hạn | “Xác nhận gửi TA” mới gửi. Chưa xác nhận thì chưa tạo ticket, chưa ai được báo. |
| Kết quả gửi | Mã yêu cầu và nhãn “Đã vào hàng chờ — TA chưa đọc” khi thao tác thành công trong mô phỏng | “Xem yêu cầu” mở lại nội dung. Nếu thất bại, giữ bản nháp và hiện “Chưa gửi được — thử lại”. |

**Ai được báo, khi nào:** sau xác nhận và gửi thành công, yêu cầu mới xuất hiện trong hàng chờ TA mô phỏng với ngữ cảnh và nguồn. Không giả lập việc gửi email/thông báo ngoài hệ thống. TA bắt đầu ca tiếp theo lúc 08:00 ngày 14/11, nhưng thời gian đọc/xử lý chưa biết. Không tự báo cả lớp. Nếu người học không làm gì, bản nháp không được gửi và FAQ không thay đổi.

**Quyết định và phương án đã loại:**

- Chọn nêu rõ phần sai đã kiểm tra được, hiện căn cứ và cho duyệt chuyển TA. Cách này giúp người học tránh ghi nhớ sai ngay, đồng thời giữ quyền sửa tài liệu cho người có thẩm quyền.
- Loại việc lặp lại nguyên văn nguồn như một bảo chứng: nguồn có thật vẫn có thể sai.
- Loại việc chỉ hỏi lại rồi chờ: người học đã chỉ rõ câu, hỏi thêm không giải quyết mâu thuẫn.
- Loại việc chỉ nói “hãy hỏi TA” rồi dừng: TA ngoài giờ và học viên vẫn cần biết câu nào không nên tin.
- Loại tự sửa tài liệu hoặc tự đăng “đính chính”: không có tool sửa; FAQ sai hoặc thiếu ngữ cảnh có thể lan rộng.

**Lỗi không cứu bằng câu chữ:** thông báo “AI có thể sai” vẫn không ngăn một bài FAQ tự xuất bản. Thiết kế cần chặn xuất bản trước TA duyệt; báo cáo nguồn sai luôn là nội dung chờ kiểm tra, không tự biến thành đính chính chính thức.

### 3.2. S02 — Xin lời giải bài đang mở

**Loại lỗi:** yêu cầu vượt phạm vi hỗ trợ; không kết luận học viên kém hoặc có ý gian lận. Nếu AI đưa đáp án thì đó là lỗi hệ thống thực thi giới hạn. Bối cảnh sát hạn giải thích nhu cầu cần giúp nhanh, không mở thêm quyền giải hộ.

**Lời AI dự kiến, nguyên văn:**

> Bài 3 đang mở, hạn nộp là 23:59 ngày 13/11/2026 theo trang khóa học. Mình có thể gợi ý bước đầu, nhưng không đưa hoặc xác nhận đáp số, cũng không viết nhận xét để bạn nộp.
>
> Bạn có thể bắt đầu bằng cách sắp xếp dãy số ở §3.5 theo thứ tự tăng dần. Sau đó đối chiếu quy tắc xác định trung vị với §3.2. Mình sẽ không tính hoặc chốt kết quả của bài đang mở.
>
> Nếu bạn đang vướng một khái niệm, hãy nói rõ khái niệm đó; mình có thể giải thích từ tài liệu. Nếu cần TA, bạn có thể xem và duyệt nội dung gửi. TA hiện ngoài giờ, nên mình không hứa có phản hồi trước hạn tối nay.

**Khi học viên tiếp tục xin xác nhận, dùng lời sau:**

> Mình chưa thể xác nhận đáp số bài đang mở, kể cả chỉ trả lời đúng hoặc sai. Bạn có thể đối chiếu định nghĩa ở §3.1 và §3.2. Mình có thể giải thích các định nghĩa đó, nhưng không kiểm lần lượt các phép tính để chốt lời giải thay bạn.

**Người học thấy và làm tiếp:**

| Vị trí dự kiến | Nội dung hiển thị | Thao tác và kết quả |
|---|---|---|
| H1 — căn cứ | “Bài 3 đang mở”, hạn lấy từ B; thẻ §3.1/§3.2/§3.5 | Mở đúng đoạn; không gắn nguồn “slide 12”. |
| H2 — sửa nhu cầu | Lựa chọn “Xem định nghĩa”, “Mình đang vướng khái niệm khác” | Xem khái niệm hoặc làm rõ câu hỏi; không mở chuỗi tính lần lượt bài 3. |
| H3 — duyệt gửi | “Soạn câu hỏi cho TA”, bản nháp sửa được và giờ trực | Chỉ gửi sau khi học viên xác nhận; có trạng thái lỗi/thành công như S01. |
| Giới hạn hành động | Không có nút “Xem đáp án”, “Chấm đáp số” hoặc “Đăng lời giải” | Yêu cầu bằng tin nhắn cũng phải bị chặn, không chỉ giấu nút. |

**Ai được báo, khi nào:** không tự báo TA chỉ vì học viên xin lời giải. Chỉ tạo yêu cầu sau khi họ duyệt gửi, dùng cùng quy trình S01. TA không được xem là người sẽ giải hộ bài mở; lời hứa chuyển chỉ là tiếp nhận câu hỏi. Nếu người học không gửi, họ vẫn đọc được tài liệu và gợi ý bước đầu, không bị khóa việc học.

**Quyết định và phương án đã loại:**

- Chọn gợi ý bước đầu kèm giới hạn, hỗ trợ khái niệm và cho lựa chọn chuyển TA. Có ích ngay mà không công bố lời giải.
- Loại giải hết vì sát hạn: mức gấp không làm hậu quả lộ đáp án đảo ngược được.
- Loại “chỉ xác nhận đúng/sai”: vẫn xác nhận kết quả của bài mở.
- Loại từ chối toàn bộ việc học: hỏi về định nghĩa có căn cứ vẫn thuộc phạm vi.
- Loại bắt TA duyệt mọi gợi ý: sau 22:00 sẽ làm trợ lý không còn giúp được nhu cầu cơ bản.

**Lỗi không cứu bằng câu chữ:** cảnh báo “chỉ tham khảo” đặt trên đáp án vẫn làm lộ đáp án. Cần chặn nội dung trước khi hiển thị, áp dụng qua các lượt hội thoại và cả luồng FAQ.

### 3.3. Ba nguyên tắc gắn với vị trí trên prototype

| Nguyên tắc | Quyết định cụ thể | Vị trí dự kiến để B dựng và chụp ảnh |
|---|---|---|
| PAIR — Explainability + Trust | Cho xem đúng căn cứ và giới hạn; phân biệt trích nguồn với phản ví dụ nhóm dựng. | H1: thẻ nguồn §3.3 hoặc trạng thái bài từ B, nhãn “cần kiểm tra/đang mở”. |
| HAX G9 — Sửa dễ dàng | Người học sửa câu hỏi/báo cáo, bỏ bản nháp trước gửi; AI không tự công bố bản sửa. | H2: nút sửa, trường nội dung và nút bỏ; sau sửa vẫn phải duyệt gửi. |
| HAX G10 — Thu hẹp phạm vi khi nghi ngờ | Không đoán nguồn không có, không chốt lời giải; chuyển câu cần thẩm quyền sau bước duyệt. | H3: giới hạn hỗ trợ, bản xem trước gửi TA và cảnh báo ngoài giờ. |

Đây là vị trí **dự kiến**; §5 phải thay bằng ảnh thật có đánh số sau khi prototype được dựng. Không ghi đã thể hiện nguyên tắc trên màn hình khi chưa kiểm tra.

### 3.4. Bốn đường trải nghiệm cần bàn giao

| Đường | Kịch bản | Hành vi |
|---|---|---|
| Bình thường | N01 | Giải thích ngắn kèm §3.1–§3.2, không chuyển TA bắt buộc. |
| Mơ hồ | S05 | Hỏi một câu làm rõ trước khi giảng. |
| Không đủ căn cứ/nguồn sai | S04/S01 | Nói rõ phần không có hoặc điểm cần kiểm tra; không bịa; cho soạn yêu cầu TA. |
| Người học sửa AI | S01 hoặc học viên sửa lại mục đang hỏi | Tiếp nhận chỉnh sửa, cập nhật bản nháp và nguồn; không tự kết luận sửa đổi luôn đúng. |

### 3.5. Cách nói và sửa phải theo đúng loại lỗi

| Loại lỗi | Tình huống dựng | Lời AI nguyên văn và cách sửa |
|---|---|---|
| Hệ thống | AI đã nhắc lại câu sai §3.3; học viên phản đối. | “Bạn nói đúng về điểm cần kiểm tra. Mình đã nhắc lại câu trong §3.3 như một kết luận chắc chắn. Mình cần đính chính: kết luận ‘luôn nhỏ hơn’ không đúng trong mọi trường hợp. Mình sẽ đánh dấu câu trả lời trước cần xem lại và cho bạn xem báo cáo trước khi gửi TA.” Giữ bản trả lời cũ có nhãn đính chính, không âm thầm sửa lịch sử. |
| Người dùng nhập nhầm | Học viên gõ “bài 2” rồi sửa “ý em là bài 3”. | “Mình đã cập nhật sang bài 3. Bài này đang mở nên mình chỉ gợi ý bước đầu, không đưa hay xác nhận đáp số.” Đọc lại trạng thái bài, bỏ bản nháp chưa gửi theo bài cũ, không giữ quyền giải bài đã đóng. Không trách người học. |
| Ngữ cảnh | Hệ thống tiếp nhận câu hỏi đúng quy trình lúc 22:30, nhưng học viên hiểu “đã gửi” là sẽ được giúp trước hạn. | “Yêu cầu đã vào hàng chờ, chưa có nghĩa TA đã đọc. TA hiện ngoài giờ; mình không cam kết có phản hồi trước 23:59 tối nay. Bạn vẫn có thể xem giải thích khái niệm từ tài liệu ngay tại đây.” Hiện ngoài giờ trước khi gửi và giữ đường tự học mở, thay vì chỉ đổi thông báo sau khi gửi. |

Nếu đáp án bài mở đã bị lộ do lỗi hệ thống, không hứa “hoàn tác là chưa từng lộ”. Dừng cung cấp tiếp, đánh dấu nội dung có vấn đề và đề nghị học viên duyệt báo cáo cho TA; TA/giảng viên quyết định cách xử lý học vụ. Prototype không tự trừ điểm hoặc kết luận gian lận.

### 3.6. Câu chữ cho các trạng thái chuyển TA

| Trạng thái | Lời hiển thị nguyên văn |
|---|---|
| Đang soạn | “Đây là bản nháp, chưa gửi TA. Bạn có thể sửa hoặc bỏ trước khi xác nhận.” |
| Đang gửi | “Đang gửi yêu cầu. Vui lòng chờ kết quả trước khi thử lại.” |
| Gửi thành công | “Đã vào hàng chờ TA · Mã yêu cầu: [mã được tạo]. TA chưa đọc. Giờ trực: 08:00–22:00; chưa có thời gian phản hồi được cam kết.” |
| Gửi thất bại | “Chưa gửi được yêu cầu. Bản nháp vẫn còn; bạn có thể sửa hoặc thử lại.” |
| Bỏ trước gửi | “Đã bỏ bản nháp. Chưa có yêu cầu nào được gửi TA.” |
| Sửa sau gửi | “Yêu cầu đã gửi được giữ lại. Bạn có thể xem nội dung; để bổ sung, hãy tạo bản nháp bổ sung và duyệt gửi. Việc bổ sung không thu hồi nội dung TA có thể đã đọc.” |

Nhãn “mô phỏng” phải hiện trên cả hai màn hình: mã yêu cầu chỉ chứng minh trạng thái trong prototype, không phải liên lạc với TA thật.

## §4. Mức tự chủ

### 4.1. Ma trận bốn tool

Quyền dưới đây là **đề xuất thiết kế của bản nháp**, chưa phải cơ chế đã được cài đặt. “Tự làm” có điều kiện, không cho phép vượt phạm vi §1. Những hành vi bị cấm được ghi riêng dù tool có mức chính là tự làm hoặc cần duyệt.

| Tool | Mức chính và điều kiện | Sai thì ai chịu, có đảo được không? | Chờ người thì mất gì? | Phương án đã loại |
|---|---|---|---|---|
| `tra_cuu_tai_lieu` | **Tự làm.** Chỉ trả đoạn có thật kèm mã mục; nếu thiếu thì báo thiếu. Gắn cờ nội dung nghi sai, không dùng “đã tìm thấy” như chứng nhận đúng. | Học viên có thể tin nhầm nếu trích sai/nguồn sai; thao tác chỉ đọc không đổi dữ liệu, nhưng nội dung đã đọc vẫn có ảnh hưởng. | Duyệt từng lần đọc làm câu hỏi đơn giản cũng phải chờ, đặc biệt ngoài giờ. | Loại bắt TA duyệt mọi truy vấn; loại tự lấy nguồn ngoài fixture để lấp chỗ trống. |
| `goi_y_bai_tap` | **Tự làm trong giới hạn.** Bài mở chỉ bước đầu và giải thích khái niệm. Kiểm trạng thái bài và lịch sử hỗ trợ trước khi gửi; không xác nhận phép tính từng bước để ghép thành đáp án. Bài đã đóng, có đáp án thì được giải thích đầy đủ từ dữ liệu có sẵn. | Học viên thấy đáp án rồi không thể “chưa thấy” lại; thu hồi tin không khôi phục tính tự làm. | Bắt duyệt mọi gợi ý khiến học viên không được hỗ trợ sau 22:00; từ chối quá rộng làm học bế tắc. | Loại tự giải không giới hạn; loại cấm mọi gợi ý hoặc đẩy tất cả cho TA. |
| `chuyen_TA` | **Cần học viên duyệt.** AI soạn bản nháp; học viên xem nội dung và ngữ cảnh rồi xác nhận gửi. Chỉ báo vào hàng chờ khi thao tác thành công. | Gửi nhầm gây mất ngữ cảnh hoặc chia sẻ thừa nội dung; có thể cập nhật yêu cầu nhưng không hứa thu hồi phần TA đã đọc. | Bước duyệt ngắn có thể chấp nhận; không bắt học viên đợi TA chỉ để gửi câu hỏi. Sau giờ trực phải chấp nhận phản hồi muộn. | Loại gửi ngầm mọi câu; loại cấm nhận yêu cầu ngoài giờ; loại hứa “đã báo” khi chỉ có bản nháp. |
| `dang_FAQ` | **Cần TA duyệt.** AI chỉ soạn nội dung đủ nguồn; TA kiểm tra và bấm xuất bản. Không công bố lời giải bài mở; nghi vấn S01 chưa xử lý không được đăng như đính chính chính thức. | Cả lớp có thể học sai. Gỡ được bài nhưng không đảo được điều người khác đã đọc hoặc sao chép. | FAQ ra muộn hơn; vẫn có thể hỗ trợ riêng bằng kiến thức đã kiểm tra. Cái giá chờ thấp hơn phát tán sai. | Loại tự xuất bản; loại để học viên duyệt thay TA; loại cấm toàn bộ FAQ vì sẽ bỏ mất tri thức đã được xác minh. |

### 4.2. Người duyệt thấy gì; nếu không duyệt kịp

| Hành động | Người duyệt | Thông tin trước khi bấm | Không duyệt / lỗi / quá giờ |
|---|---|---|---|
| Gửi câu hỏi tới TA | Học viên | Nội dung hỏi, đoạn nguồn liên quan, trạng thái bài, người nhận, giờ trực và cảnh báo không cam kết thời gian trả lời. | Không bấm: giữ nháp, không gửi. Lỗi: giữ nháp, cho thử lại. Ngoài giờ: nhận hàng chờ, không tự gia hạn bài. |
| Đăng FAQ | TA | Bản dự thảo, nguồn, trạng thái bài, cờ nghi sai và phạm vi nội dung sẽ công khai. Không đưa thông tin định danh không cần thiết lên FAQ. | Chưa duyệt: giữ nháp, không tự xuất bản theo thời gian. Thiếu nguồn hoặc chứa lời giải bài mở: trả về sửa/chặn, kể cả có yêu cầu của học viên. |

**Cấm trong mọi trường hợp của thiết kế:** tự sửa tài liệu, tự gia hạn; bịa nguồn; đưa/xác nhận đáp số hoặc nhận xét hộ bài mở; tự xuất bản FAQ chưa duyệt. Một nút “tôi đồng ý” của học viên không mở khóa các hành vi này.

### 4.3. Tool khó xếp nhất: `goi_y_bai_tap`

Ba cách cân nhắc:

1. **Tự giải theo yêu cầu:** nhanh nhưng thất bại ở S02/S03; đáp án lộ không thu hồi được.
2. **Mọi gợi ý cần TA duyệt:** kiểm soát chặt hơn nhưng thất bại với nhu cầu học tối muộn; N01 cũng có thể bị chờ vô ích.
3. **Tự gợi ý có ranh giới nội dung:** phương án cả hai thành viên đã chọn. Bước đầu hỗ trợ được ngay; yêu cầu giải/chấm bài bị chặn, câu khái niệm có nguồn vẫn được đáp.

Đổi lại, cách 3 cần kiểm soát nhiều lượt: không để mỗi lượt “chỉ thêm một bước” cuối cùng thành cả bài. Với prototype mô phỏng, B cần dựng yêu cầu lặp và đường chặn rõ; không tuyên bố đã giải quyết mọi cách lách bằng ngôn ngữ tự nhiên.

**Lựa chọn của từng thành viên:** Hà Lê Duy (A) và Nguyễn Thiên Bảo (B) đều chọn phương án 3: AI được tự gợi ý trong giới hạn, không đưa hoặc xác nhận đáp số bài đang mở. Bảo đã xác nhận lựa chọn này. Hai thành viên không có bất đồng về mức tự chủ của tool; khác biệt giữa các phương án vẫn được phân tích để làm rõ cái giá của từng cách, không dựng ra một cuộc tranh luận không có thật.

**Lý do chọn:** Với người học hỏi lúc 22:30, yêu cầu TA duyệt mọi gợi ý sẽ khiến hỗ trợ cơ bản bị gián đoạn vì TA đã hết ca lúc 22:00. Ngược lại, cho AI tự giải không giới hạn sẽ làm lộ lời giải ở S02/S03. Phương án 3 giữ được trợ giúp ngay cho câu khái niệm và bước đầu, đồng thời giới hạn những nội dung không thể thu hồi sau khi học viên đã đọc.

**Cách chốt và chuyển thành yêu cầu triển khai:** Dùng phương án 3 làm cơ sở bàn giao. Giữ hỗ trợ ngay cho N01 và phần khái niệm có nguồn; với bài mở, chỉ đưa bước đầu, không tăng dần tới kết quả qua các lượt. Nội dung cần thẩm quyền được soạn thành bản nháp để học viên duyệt chuyển TA; FAQ vẫn cần TA duyệt. Nếu prototype chưa kiểm soát được yêu cầu lặp, thu hẹp về giải thích khái niệm thay vì tiếp tục sinh các bước giải. Cách này cân bằng cái giá lộ đáp án ở S02/S03 với cái giá chờ vô ích ở S10.

**Điểm B cần chứng minh trên prototype:** Không chỉ giấu nút xem đáp án mà còn chặn xin xác nhận kết quả và yêu cầu giải từng bước liên tiếp. Sự đồng thuận về phương án thiết kế không thay thế cho kiểm tra hành vi thực tế; kết quả kiểm tra sẽ được ghi ở §5–§6 sau khi triển khai.

### 4.4. Thử mức tự chủ trên ba ca — duyệt thiết kế trên giấy

Bảng này là kiểm tra logic dự kiến; chưa phải kết quả chạy prototype.

| Ca | Chuỗi hành động dự kiến | Sai đã bị chặn thế nào? | Còn tự làm khi cần hỏi/duyệt không? | Có bắt chờ vô ích không? |
|---|---|---|---|---|
| S01 — nguồn sai | Tự tra §3.3 → hiện nghi vấn và phản ví dụ → soạn báo cáo → học viên duyệt gửi → TA nhận hàng chờ. FAQ giữ nháp tới khi kiểm tra/duyệt. | Không lặp câu sai thành bảo chứng; không tự công bố đính chính. Cần B thử cả đường gửi lỗi và FAQ. | Không tự sửa tài liệu/gửi báo cáo/đăng FAQ. Người học không bấm thì chưa gửi. | Học viên biết ngay câu nào cần xem lại; chỉ phần xác minh chính thức chờ TA. |
| S02 — bài mở | Đọc B và §3.5 → nêu giới hạn → gợi ý bước đầu → chặn xin đáp số/xác nhận lặp lại → chuyển TA chỉ khi học viên muốn và duyệt. | Chặn lời giải trước hiển thị và trên FAQ; không xem xác thực người học là quyền giải hộ. | Không gửi TA ngầm, không dùng học viên duyệt để mở khóa đáp án. | Không cần TA duyệt định nghĩa/gợi ý bước đầu có nguồn. |
| N01 — hỏi khái niệm | Tự tra §3.1–§3.2 → giải thích trung bình/trung vị, kèm nguồn. | Không kéo câu hỏi thành lời giải số liệu §3.5; không thêm nguồn ngoài fixture. | Không cần hỏi lại vì yêu cầu đã rõ; không có hành động công khai cần duyệt. | Trả lời ngay, không chuyển TA bắt buộc. |

**Điểm cần B kiểm chứng:** yêu cầu lặp lại không rò đáp án; tin nhắn không vượt quyền dù nút đã bị ẩn; gửi lỗi không báo thành công; đổi màn hình không làm ticket trùng/mất; FAQ không tự xuất bản. Nếu prototype chưa chặn được thì phải ghi lỗi còn lại ở §6 và sửa, không coi bảng này là bằng chứng chạy đạt.

### 4.5. Luật bổ sung và tách bước

Giữ bốn tool gốc. Bổ sung các bước nội bộ **soạn bản nháp → xem trước → duyệt → thực thi** cho chuyển TA và FAQ; soạn nháp không được tính là tool đã gửi hoặc đã đăng. Đây là thay đổi luồng được khai báo, không giả một tool gửi có khả năng thu hồi.

Trạng thái đề xuất: yêu cầu `draft → queued → reviewed`; gửi lỗi giữ `draft` kèm lỗi. FAQ `draft → published` chỉ sau TA duyệt và nội dung vượt qua giới hạn bài mở/nguồn. B có thể bổ sung trạng thái sửa lỗi nếu ghi rõ và không đổi quyền tự chủ.

Trước mỗi gợi ý, kiểm trạng thái bài và phần trợ giúp đã cung cấp. Nếu thiếu trạng thái bài, hỏi bài nào hoặc chỉ giải thích khái niệm; không mặc định bài đã đóng. Không tự suy ra quy ước mẫu/tổng thể hay hàm Excel từ câu hỏi S07.

### 4.6. Lời hứa sản phẩm sau khi giới hạn tự chủ

> Mình là trợ lý AI hỗ trợ học từ tài liệu khóa học và sẽ chỉ rõ nguồn, phần chưa có căn cứ hoặc cần xem lại. Với bài đang mở, mình chỉ gợi ý bước đầu, không đưa hay xác nhận đáp số. Bạn quyết định gửi câu hỏi cho TA sau khi xem nội dung; gửi thành công có nghĩa vào hàng chờ, chưa có nghĩa TA đã đọc hoặc hứa trả lời trước hạn.

Mức tự chủ chuyển lời hứa từ “AI giải quyết mọi câu hỏi ngay” sang hỗ trợ có căn cứ và có giới hạn cụ thể. FAQ cần TA duyệt để kiến thức công khai không phụ thuộc riêng vào quyết định của AI. Lời hứa này phải hiện trên giao diện và khớp hành vi thật của bản mô phỏng.

### 4.7. Các điều kiện không được phá vỡ khi triển khai

1. **Duyệt gắn với đúng nội dung.** Nếu học viên sửa bản nháp sau khi xem trước, phải xem và xác nhận bản mới. Không lấy xác nhận cũ để gửi nội dung đã đổi.
2. **Chưa thành công thì chưa báo đã gửi.** Trong lúc gửi khóa thao tác gửi lặp. Khi kết quả chưa rõ, kiểm tra lại yêu cầu trước khi tạo bản mới; không gắn “thất bại” rồi âm thầm gửi trùng.
3. **Chuyển màn hình không đổi quyền.** Màn hình TA là góc nhìn mô phỏng cho demo, không phải chứng minh xác thực hay bảo mật thật. Nút xuất bản chỉ nằm ở góc nhìn TA và vẫn kiểm giới hạn nội dung.
4. **Sửa câu hỏi phải đánh giá lại phạm vi.** Đổi bài 2 sang bài 3, đổi nguồn hoặc đổi yêu cầu thì kiểm lại trạng thái và quyền; không dùng kết quả cho bài trước.
5. **Không tự sửa lịch sử đã gửi.** Bỏ bản nháp chỉ hủy trước khi gửi. Bổ sung sau gửi tạo bản nháp mới liên kết yêu cầu gốc; học viên xem và duyệt riêng. Không tuyên bố có tool thu hồi hay sửa ticket từ xa mà đề chưa cấp.
6. **“Tự làm có thể sửa” không đồng nghĩa mọi hậu quả đều hoàn tác được.** Đọc nguồn không thay dữ liệu; gợi ý đã đọc không thu hồi khỏi người học được. Có thể dừng gợi ý, sửa nhu cầu, đánh dấu đính chính; không đặt nút hoàn tác giả cho kiến thức đã lộ.

Các bước xử lý trạng thái ở đây là luật thiết kế bổ sung cho prototype, không phải dữ liệu hay tool mới do đề cung cấp. Trường hợp kết quả gửi chưa rõ cần hiện “Chưa xác định được kết quả gửi”, tránh báo sai trạng thái; nếu B chưa dựng được thì ghi giới hạn trong §5–§6.

---

**Bàn giao cho B — chưa thuộc phần đã triển khai:** dùng S01/S02 và N01; dựng đủ bốn đường ở §3.4; giữ mã H1–H3 khi đánh số ảnh; đối chiếu mọi nút với §4. B bổ sung §5–§7 vào bản cuối, kèm ảnh thật, kết quả thử thực tế và ca lạ nhận được trong demo. Không sao chép nhãn “đã chạy đạt” từ bảng dự kiến.
