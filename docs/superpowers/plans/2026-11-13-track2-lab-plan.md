# Kế hoạch hoàn thành LAB5 — T2 Giáo dục — nhóm 2 người

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Hoàn thành spec, prototype 1–2 màn hình và demo cho trợ lý học bài tối muộn; chứng minh cách xử lý tài liệu sai, bảo vệ bài tập đang mở và chuyển TA trung thực.

**Architecture:** Prototype tĩnh với dữ liệu dựng cố định, các trạng thái hội thoại và hàng chờ TA mô phỏng dùng chung dữ liệu. Hai màn hình: học viên và TA. Chưa triển khai sản phẩm hoặc gọi AI trong bước lập kế hoạch này.

**Tech Stack:** Đề xuất HTML/CSS/JavaScript thuần, không backend, không cần tài khoản hay API key. Dùng trình duyệt để kiểm tra tương tác.

**Spec:** `tracks/t2-education.md`, `01-challenge-brief.md`, `02-guide.md`, `03-spec-template.md`, `04-rubric.md` trong repo đề bài. Các quyết định bên dưới là đề xuất thiết kế, chưa phải quyết định đã được nhóm thông qua.

## Quy trình duyệt — cập nhật theo yêu cầu mới

- Hiểu “1, 2, 3, 4” là §1–§4 của spec: A (bạn) sở hữu; B sở hữu §5–§7 và toàn bộ prototype.
- Hiện chỉ cập nhật kế hoạch. Chờ bạn duyệt kế hoạch trước khi viết nội dung bài nộp hoặc triển khai.
- Khi thực hiện, hoàn thành bản nháp §1–§4, tự kiểm theo rubric rồi gửi bạn duyệt cùng danh sách file và nội dung đã đổi.
- Nếu còn yêu cầu sửa, cập nhật bản nháp và báo lại thay đổi; không tự xem im lặng là đồng ý.
- **Chỉ commit khi bạn đồng ý rõ ràng sau khi xem kết quả.** Không tự stage, commit, push, tạo PR hoặc công khai bài nộp trong bước lập kế hoạch/duyệt.
- Nếu triển khai sau này, quy tắc chờ duyệt trước commit này ưu tiên hơn các bước commit trong skill thực thi.

## Các điểm thay đổi so với kế hoạch trước

| Nội dung | Trước | Nay |
|---|---|---|
| §4 — Mức tự chủ | B chủ trì | A chủ trì, B đọc chéo để triển khai đúng |
| Màn hình học viên | A dựng | B dựng theo câu chữ và luồng A bàn giao |
| §5 — Prototype | Cả hai cùng sở hữu | B sở hữu; A đối chiếu với §3–§4 |
| §6–§7 | B chủ trì | Giữ nguyên B chủ trì |
| Cách chạy công việc | §2–§3 và §4 làm song song | A làm §1→§2→§3→§4; B có thể dựng khung, chờ duyệt hợp đồng hành vi trước khi ráp luồng |
| Bàn giao | Chia màn hình theo người | A bàn giao đặc tả; B triển khai và cung cấp bằng chứng |
| Commit | Chưa quy định mốc duyệt cụ thể | Kết quả phải được bạn duyệt rồi mới được commit |

Phạm vi T2, fixture, hai ca S01/S02 và hướng HTML mô phỏng giữ nguyên dạng đề xuất.

## Global Constraints

- Giữ nguyên lát cắt được giao trong T2; chỉ dùng fixture của đề và dữ liệu giả có ghi nhãn.
- Đề yêu cầu đúng 3 người. Kế hoạch chia cho 2 người theo yêu cầu người dùng; cần xác nhận ngoại lệ với TA. Không tạo thành viên thứ ba giả.
- Bài tập 3 đang mở, hạn 13/11/2026 23:59; bài tập 2 đã đóng và có đáp án. Giờ TA 08:00–22:00.
- Dùng đồng hồ mô phỏng cố định: 22:30 ngày 13/11/2026, giờ Việt Nam. Hiện nhãn mô phỏng; không để thời gian máy làm thay đổi demo.
- Không đưa hoặc xác nhận đáp số bài đang mở, không viết nhận xét hộ; chuỗi câu hỏi nhỏ cũng không được lách quy tắc này.
- Chỉ có nội dung chi tiết buổi 3 trong fixture; biết buổi 1–2 đã mở không có nghĩa được tự bịa nội dung của chúng.
- Không bịa slide, trích dẫn, hàm Excel hoặc thời gian phản hồi chính xác mà fixture không cấp.
- Sau 22:00, tiếp nhận yêu cầu là đưa vào hàng chờ, không có nghĩa TA đã đọc. 08:00 hôm sau là lúc bắt đầu ca trực, không phải cam kết trả lời ngay.
- Repo nộp mới, công khai, tên `K5-<lớp>-Day05-T2-<tên nhóm>`; không đẩy toàn bộ repo đề lên làm bài nộp.
- Không API thật trong bản cơ sở; nếu thêm bonus phải có nơi giữ secret phía máy chủ, giới hạn thời gian và bằng chứng chạy thật.

## Hướng thiết kế đề xuất

Ba cách cân nhắc:

1. Figma: nhanh để vẽ nhưng khó thể hiện đầy đủ chuyển trạng thái và hàng chờ nhất quán.
2. HTML/CSS/JS mô phỏng: dễ mở, không phụ thuộc dịch vụ, đủ để chứng minh UX và tự chủ. **Đề xuất chọn.**
3. AI thật: có bonus +3 nhưng thêm tích hợp, chi phí và đầu ra bất định. Chỉ làm sau khi bản cơ sở đạt.

Ba việc không làm: giải/nộp hộ bài đang mở; giảng nội dung chưa có trong tài liệu; tự công bố kiến thức cho cả lớp hoặc tự sửa tài liệu gốc.

Luồng màn hình:

`Học viên hỏi → kiểm tra nguồn và trạng thái bài → trả lời/hỏi lại/giới hạn → học viên duyệt chuyển → hàng chờ TA → TA xử lý hoặc duyệt FAQ mô phỏng`.

Hai ca trọng tâm đề xuất:

- **S01 — Tài liệu sai:** Học viên hỏi về câu “độ lệch chuẩn luôn nhỏ hơn phương sai” ở §3.3. Hậu quả: học sai rồi lan qua FAQ. Hiện nguyên văn nguồn, đánh dấu phần cần xem lại, không khẳng định nguồn luôn đúng; cho xem và gửi báo cáo tới TA. Ví dụ kiểm tra do nhóm dựng: phương sai 0,25 thì căn bậc hai là 0,5; ghi rõ đây là phản ví dụ kiểm tra, không giả làm trích dẫn tài liệu.
- **S02 — Xin xác nhận đáp số bài 3:** Học viên muốn đáp án hoặc xác nhận con số, gây lộ lời giải khi bài đang mở. Nêu trạng thái bài và hạn, từ chối xác nhận, chỉ gợi ý bước đầu từ §3.1/§3.2; không lộ đáp án qua nút, FAQ hoặc gợi ý liên tiếp.
- Khi chốt spec, so với ứng viên gần nhất: hạn nộp bị nói sai hoặc hứa TA trả lời trước hạn. Ghi lý do chọn hai ca trên; nhóm có thể đổi thứ tự ưu tiên nếu lập luận tốt hơn.

## Chia công việc theo mục bài nộp

| Người | Sở hữu chính | Phần bài nộp | Phần demo |
|---|---|---|---|
| A — bạn | Phạm vi, kịch bản, UX khi sai, mức tự chủ | §1, §2, §3, §4 và đặc tả bàn giao | Phạm vi, hai ca khó, lập luận quyền tool |
| B — bạn cùng nhóm | Toàn bộ prototype, bằng chứng, tiêu chí đạt và demo | §5, §6, §7; cả hai màn hình | Bấm luồng, vị trí HAX/PAIR, kết quả kiểm tra và ca lạ |
| Cả hai | Chốt hành vi và kiểm tra chéo | Đối chiếu §1–§4 với §5–§7, ráp bài | Mỗi người giải thích được phần đứng tên |

Chia theo yêu cầu của bạn, không khẳng định số mục đồng nghĩa khối lượng chính xác 50/50. A có phần thiết kế/lập luận; B có phần dựng, kiểm tra và lập luận giao diện. Không ghi cuộc thảo luận hoặc lựa chọn cá nhân như đã diễn ra nếu chưa thực sự làm.

## Checklist riêng của A — làm lần lượt, bàn giao được từng phần

### A1 — §1: Lát cắt và phạm vi

- [ ] Chép đúng lát cắt T2; nêu người dùng, công việc, quyết định AI và kết quả.
- [ ] Viết 3 việc không làm kèm lý do theo rủi ro; chốt danh sách 4 tool gốc.
- [ ] Ghi bảng thành viên đúng người thật, để trống dữ liệu cá nhân chưa có.
- [ ] Kiểm tra: không biến bài thành chatbot tổng quát hoặc công cụ giải hộ.

**Bàn giao:** §1 và danh sách phạm vi cấm để B không tạo nút vi phạm.

### A2 — §2: Kịch bản và ưu tiên

- [ ] Soạn 10 ca S01–S10 theo Task 2; kiểm đủ 4 lớp, mỗi ca trỏ về tool hoặc dữ liệu.
- [ ] Gắn mức hại, chỉ rõ người chịu và hậu quả; tách lỗi kiến thức khỏi lỗi thực thi.
- [ ] Chọn S01/S02, so với ca suýt chọn và viết lý do; thêm ca bình thường để thử mức tự chủ.
- [ ] Kiểm tra: mỗi ca có hành vi tốt cụ thể, không dùng câu chung “AI có thể sai”.

**Bàn giao:** bảng kịch bản với mã ổn định, hai ca demo chính và ca bình thường.

### A3 — §3: UX khi AI sai

- [ ] Với mỗi ca chính, viết tin người dùng và lời AI nguyên văn.
- [ ] Liệt kê nguồn/nhãn/nút người dùng thấy; mỗi nút ghi thao tác và kết quả.
- [ ] Ghi người được báo, thời điểm, ngoài giờ và gửi thất bại; không hứa TA xử lý trước hạn.
- [ ] Phân loại lỗi, so sánh hỏi lại/trả lời giới hạn/chuyển người; ghi lý do loại phương án khác.
- [ ] Gắn G10, G9, PAIR vào các vị trí dự kiến H1/H2/H3; B sẽ dùng cùng mã trên ảnh.
- [ ] Nêu lỗi câu chữ không cứu được và cơ chế chặn: nguồn sai không tự lan sang FAQ; bài mở không bị lộ qua gợi ý liên tiếp.

**Bàn giao:** lời AI đã chốt, bảng trạng thái/nút, mã H1–H3. Đây là đặc tả dự kiến, chưa phải ảnh hoặc bằng chứng đã triển khai.

### A4 — §4: Quyền tool và thử quyết định

- [ ] Viết bảng 4 tool: mức, điều kiện, hậu quả sai, khả năng đảo, cái giá khi chờ.
- [ ] Với tool cần duyệt: ai duyệt, thấy gì, không duyệt thì sao; khai báo nếu tách bước.
- [ ] Chốt tool khó xếp nhất và phương án đã loại; thu ý kiến thật của B nếu muốn ghi bất đồng nhóm.
- [ ] Thử trên S01/S02 và ca bình thường theo đủ 3 câu rubric.
- [ ] Viết lời hứa sản phẩm sau khi giới hạn tự chủ; đối chiếu lại §3 để không mâu thuẫn.

**Bàn giao:** ma trận quyền, sơ đồ trạng thái, quy tắc cấm và bảng thử 3 ca để B triển khai/viết §6.

### A5 — Tự kiểm và gửi duyệt

- [ ] Kiểm R1–R4: tổng trọng số 65 điểm, không tự tuyên bố đạt điểm khi chưa chấm.
- [ ] Đưa bạn bản nháp §1–§4, nội dung thay đổi, câu hỏi còn mở và danh sách file đã tạo/sửa.
- [ ] Chờ bạn duyệt nội dung; sửa nếu có yêu cầu. Chỉ commit sau khi bạn đồng ý rõ ràng.
- [ ] B nhận đặc tả đã duyệt; thay đổi hành vi phát sinh phải báo lại để cập nhật cả spec và prototype.

## File Structure — trong repo nộp mới

- `spec.md`: 7 mục theo mẫu, bảng hai thành viên thật; các trường tên, mã học viên, lớp và ngoại lệ nhóm phải xác nhận.
- `prototype/index.html`: hai màn hình và các nút điều khiển demo.
- `prototype/styles.css`: bố cục, trạng thái và chú thích đánh số.
- `prototype/fixtures.js`: tài liệu §3.1–§3.5, lịch, giờ TA, thời gian mô phỏng, kịch bản.
- `prototype/app.js`: trạng thái hội thoại, tạo yêu cầu, duyệt FAQ, reset.
- `prototype/README.md`: cách mở, giới hạn mô phỏng, đường demo và liên kết ảnh.
- `prototype/screenshots/01-student.png`, `02-ta.png`: ảnh thực tế sau khi kiểm tra, đánh số khớp §5.

## Task 1 — Chốt dữ liệu và hợp đồng bàn giao (cả hai, 20 phút)

- [ ] Đọc lại T2 và rubric; thống nhất hướng mô phỏng, hai ca khó và 3 việc không làm.
- [ ] A tạo §1 và bảng thành viên; B kiểm tra dữ liệu hạn, giờ TA, quyền tool.
- [ ] Xác nhận với TA ngoại lệ hai thành viên; ghi kết quả thật, không tự coi như được miễn.
- [ ] Cùng chốt hợp đồng dữ liệu: scenario `{id, message, sourceIds, exerciseStatus, riskClass, expectedAction}`; ticket `{id, scenarioId, summary, sourceIds, status}`.
- [ ] Chốt ticket có trạng thái `draft`, `queued`, `reviewed`; FAQ `draft`, `published`. Gửi lỗi không được đổi thành `queued`.

**Nghiệm thu:** Cả hai dùng cùng mã S01/S02, cùng fixture và cùng ý nghĩa trạng thái; không suy diễn 08:00 là giờ trả lời chắc chắn.

## Task 2 — Kịch bản và UX khi sai (A chủ trì, 40 phút)

- [ ] Viết 10 kịch bản, mỗi dòng có tin nhắn, lớp ①–④, tool/dữ liệu liên quan, lỗi dự kiến, hành vi tốt và nhãn mức hại.
- [ ] Bộ gợi ý: S01 tài liệu sai; S02 xin đáp số; S03 xin xác nhận đáp số; S04 nhắc slide 12; S05 “độ lệch ấy”; S06 hỏi p-value; S07 hỏi hạn kèm hàm Excel; S08 học viên tự chê mình; S09 xin đăng lời giải lên FAQ; S10 hỏi sau giờ TA nhưng sắp hết hạn.
- [ ] Đánh dấu rõ từng lớp, đảm bảo đủ nguồn sự thật, mơ hồ, thẩm quyền và đặc thù giáo dục; bổ sung ca bình thường so sánh trung vị/trung bình nếu cần.
- [ ] Với S01/S02, viết nguyên văn lời AI, trạng thái màn hình, nút tiếp theo, ai được báo và khi nào; nếu không tự báo thì ghi rõ.
- [ ] Với mỗi quyết định, ghi phương án đã cân nhắc, cách chọn, bằng chứng và lý do loại; phân biệt lỗi hệ thống/người dùng/ngữ cảnh, không đổ lỗi học viên.
- [ ] Chọn G10, G9 và PAIR Explainability + Trust; đặt số chú thích cho chỗ hỏi lại/giới hạn, sửa/gửi lại và xem căn cứ.
- [ ] B đọc chéo: câu chữ có hứa việc tool chưa làm hoặc vô tình xác nhận đáp án không?

**Nghiệm thu:** ≥8 ca phủ đủ 4 lớp; hai ca khó có đầy đủ UX và lập luận; lỗi tài liệu sai có cơ chế gắn cờ/chặn lan truyền, không chỉ xin lỗi.

## Task 3 — Mức tự chủ (A chủ trì) và tiêu chí đạt (B nhận bàn giao)

- [ ] Mỗi người độc lập xếp 4 tool, so sánh thật rồi ghi điểm khác biệt. Không bịa kết quả thảo luận.
- [ ] Đề xuất `tra_cuu_tai_lieu`: tự làm, giới hạn đúng nguồn có sẵn; đọc được nguồn không có nghĩa nguồn luôn đúng.
- [ ] Đề xuất `goi_y_bai_tap`: tự làm có ràng buộc bước đầu cho bài mở; không gửi đáp số/xác nhận/nhận xét hộ. Chọn làm tool khó xếp nhất: gợi ý quá ít gây bế tắc, quá nhiều thành giải hộ; bắt TA duyệt mọi gợi ý lại gây chờ vô ích.
- [ ] Đề xuất `chuyen_TA`: học viên xem và duyệt nội dung gửi; bản nháp có thể sửa/bỏ. Khi gửi thành công mới hiện mã hàng chờ; lỗi gửi giữ bản nháp và cho thử lại.
- [ ] Đề xuất `dang_FAQ`: cần TA duyệt; AI không tự xuất bản, nội dung bài đang mở không được xuất bản. Nếu tách soạn/gửi hoặc thêm bước, khai báo rõ trong §4.
- [ ] Mỗi tool ghi ai chịu thiệt khi sai, có đảo được không, chờ mất gì, ai duyệt, thấy gì và khi không duyệt thì sao.
- [ ] Thử mức trên S01, S02 và ca bình thường; trả lời đủ ba câu rubric: chặn sai chưa, còn tự làm khi cần hỏi không, có chờ vô ích không.
- [ ] Viết lời hứa sản phẩm: “Hỗ trợ học dựa trên tài liệu và chỉ rõ giới hạn; câu cần TA sẽ được đưa vào hàng chờ sau khi bạn xác nhận.”
- [ ] Chốt 3 tiêu chí: không lộ/xác nhận đáp số bài mở; nội dung có căn cứ hoặc báo thiếu/nghi sai; trạng thái chuyển TA và quyền xuất bản đúng thực tế mô phỏng. Chấm từng tiêu chí trên S01/S02, ghi lỗi còn lại.

**Nghiệm thu:** 4/4 tool có mức và lập luận; chỉ rõ phạm vi cấm, người duyệt, trường hợp quá hạn; có bảng thử 3 ca và ma trận 2 ca × 3 tiêu chí.

## Task 4 — Dựng prototype (B chủ trì, 60 phút; A đọc chéo)

**Interfaces:** A bàn giao câu chữ, trạng thái và ma trận quyền; B sở hữu toàn bộ mã prototype. Cùng chốt `createTicket(draft) -> ticket`, `reviewTicket(id) -> ticket`, `publishFAQ(id) -> result`, `resetDemo()`. Một ticket chỉ tạo một lần cho một thao tác gửi; đổi tab không làm mất nó.

- [ ] Tạo file trong repo nộp mới, nhập fixture nguyên văn; gắn nhãn “Dữ liệu dựng · prototype mô phỏng”.
- [ ] B dựng màn hình học viên theo §3–§4 A bàn giao: nhận diện AI, chọn ca, tin nhắn, nguồn mở xem được, nhãn giới hạn, bước gợi ý, sửa/bỏ/gửi TA.
- [ ] B dựng màn hình TA: hàng chờ thực sự nhận cùng ticket mô phỏng, ngữ cảnh và nguồn, thời gian tiếp nhận, duyệt nội dung FAQ; không cho học viên tự duyệt.
- [ ] Kết nối S01: xem nghi vấn nguồn → xem/sửa báo cáo → duyệt gửi → có ticket → TA thấy đúng nội dung; cảnh báo TA ngoài giờ và không hứa trước hạn bài.
- [ ] Kết nối S02: nhận diện bài mở → không xác nhận đáp số → gợi ý bước đầu; yêu cầu lặp lại vẫn không lộ kết quả. FAQ bài mở bị chặn cả khi đổi tab.
- [ ] Thêm đường bình thường, thiếu căn cứ, mơ hồ và người dùng sửa AI; ca không hỗ trợ được hỏi làm rõ hoặc đưa vào bản nháp cho TA, không giả hiểu mọi câu.
- [ ] Thêm gửi thất bại, thử lại và reset; thao tác hủy bản nháp là hủy trước gửi, không giả thu hồi điều TA đã đọc.

**Nghiệm thu:** Bấm hết hai ca không sửa dữ liệu bằng tay; ít nhất hai mức tự chủ hiện rõ. Nếu người dùng tự do nhập, công bố giới hạn xử lý; không giả chatbot tổng quát.

## Review Focus và Task 5 — Kiểm tra chéo (A+B, 25 phút)

Năm nhóm lỗi cần thử trực tiếp:

- [ ] **Lách bài mở:** hỏi đáp số, hỏi “đúng không”, chia nhỏ lời giải, xin FAQ. Kỳ vọng không lộ/xác nhận kết quả hay nhận xét hộ.
- [ ] **Nguồn sai/không có:** §3.3 sai, slide 12 không tồn tại, hàm Excel không được cấp. Kỳ vọng gắn cờ đúng câu hoặc nói thiếu căn cứ, không bịa trích dẫn.
- [ ] **Ngoài giờ/sát hạn:** 22:30, bài hạn 23:59, TA mở lại 08:00 hôm sau. Kỳ vọng không hứa trả lời kịp hạn hoặc tự gia hạn bài.
- [ ] **Đồng bộ và gửi lỗi:** bấm gửi hai lần, đổi màn hình, gửi thất bại, reset. Kỳ vọng không ticket trùng, không báo gửi thành công sai, không mất ngữ cảnh giữa hai màn hình.
- [ ] **Quyền và ca lạ:** học viên muốn tự đăng FAQ, TA chưa duyệt, tin mơ hồ hoặc tự chê bản thân. Kỳ vọng chặn xuất bản trái quyền, hỏi lại hữu ích, không phán xét năng lực.
- [ ] A đối chiếu cả hai màn hình với §3–§4; B thử tương tác, sửa lỗi và ghi kết quả thực tế.
- [ ] Thử riêng ca bình thường để tránh thiết kế chuyển TA mọi câu.

Đây là prototype thấp rủi ro: kiểm tra tương tác và bằng chứng là chính; không dựng bộ kiểm thử lớn chỉ để kiểm các màn hình tĩnh.

## Task 6 — Đóng gói và demo (A+B, 25 phút)

- [ ] Ghép §1–§7 theo mẫu, kiểm mã kịch bản và quyết định trong spec khớp nút/luồng thật.
- [ ] Chụp hai ảnh, đánh số G10/G9/PAIR; viết §5: mỗi số thể hiện nguyên tắc và mức tự chủ gì, cách hiện khác đã loại và lý do.
- [ ] README ghi cách mở, toàn bộ phần mock, trạng thái không backend/AI thật; xác nhận link không yêu cầu tài khoản người làm.
- [ ] Chuẩn bị demo khoảng 4 phút: A 30 giây phạm vi + 90 giây hai ca/UX/quyền tool; B 60 giây bấm prototype và bằng chứng; 60 giây ca lạ và tiêu chí đạt.
- [ ] §7 chỉ ghi ca lạ thực sự nhận được sau demo; trước demo ghi “chưa diễn ra”, không dựng kết quả.
- [ ] Kiểm repo công khai bằng cửa sổ ẩn danh; bảng thành viên và mã học viên chính xác; không chứa đề hoặc secret.
- [ ] Nộp đúng kênh giảng viên, trước 23:59 ngày 13/11/2026 nếu là L3B. Xác nhận lớp trước khi đặt tên repo.

## Nhịp làm việc và điểm cắt

Ước tính khung 240 phút: 15 phút chốt; 65 phút A làm §1–§4 trong khi B chuẩn bị khung prototype và dàn ý §5–§7; 60 phút B ráp luồng theo đặc tả, A đọc chéo; 25 phút kiểm tra; 20 phút đóng gói; 15 phút nghỉ/dự phòng; 10 phút linh hoạt; 30 phút demo. Đây là thời gian làm việc ước tính, không tính thời gian chờ bạn duyệt; nếu vượt lịch cần điều chỉnh công khai.

M1: kịch bản đủ 4 lớp và hai ca khó. M2: tool có mức, thử 3 ca. M3: prototype bấm được và nguyên tắc chỉ được trên màn hình.

Nếu trễ: bỏ AI thật, trang trí, thêm tính năng; giữ UX ca khó, quyết định tự chủ, demo và bằng chứng. Bonus demo trước lớp +5 nên ưu tiên trước tích hợp AI +3; tổng sau bonus không vượt 100. Màn hình TA là hỗ trợ chứng minh, không mặc định được cộng điểm riêng.

## Việc cần nhóm xác nhận khi bắt đầu thực hiện

- Tên, mã học viên, lớp, tên nhóm; TA có chấp nhận hai người không.
- Hướng đề xuất HTML mô phỏng và phân công A/B có phù hợp thế mạnh hai người không.
- Mốc thời gian là ước tính thực hiện, không phải báo cáo các bước đã hoàn thành. Chưa tạo repo nộp, chưa triển khai prototype và chưa chấm đạt sản phẩm.
