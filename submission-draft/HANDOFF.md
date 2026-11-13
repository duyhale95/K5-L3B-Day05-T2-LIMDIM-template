# Bàn giao LAB5 Track 2 — Hà Lê Duy → Nguyễn Thiên Bảo

> **Tài liệu bàn giao ban đầu — giữ để tham chiếu lịch sử.** Các mục “cần dựng/chưa có prototype” bên dưới mô tả thời điểm Duy bàn giao. Hiện Bảo đã bổ sung prototype, ảnh và §5–§7 ở commit `e6a9dcb`; xem trạng thái hiện tại ở `REVIEW.md`. Lượt rà tiếp theo đã chỉnh câu chữ, thêm kiểm tra X4/X5 và chạy lại 17/17 PASS; đây chưa phải xác nhận demo hoặc nộp bài.

**Người bàn giao:** Hà Lê Duy · 2A202603851 · GitHub: duyhale95

**Người nhận:** Nguyễn Thiên Bảo · 2A202603861 · GitHub: Limdim1604

**Mục đích:** Bảo nhận phần thiết kế đã soạn để dựng prototype và hoàn thành §5–§7. Bộ tài liệu chưa phải bài nộp cuối.

Đọc `spec.md` trước. File này chỉ chỉ dẫn triển khai; khi có mâu thuẫn, báo lại A để cùng sửa, không tự đổi quyền tool hoặc lời hứa sản phẩm. Chưa có prototype, ảnh thật hay kết quả kiểm thử tương tác trong bộ tài liệu này.

**Sẵn sàng bàn giao thiết kế:** Hà Lê Duy phụ trách §1–§4; Nguyễn Thiên Bảo nhận prototype và §5–§7. Duy và Bảo đều chọn phương án 3 cho `goi_y_bai_tap`, Bảo đã xác nhận theo thông tin Duy cung cấp. B có thể bắt đầu triển khai theo đặc tả này. Tên nhóm, lớp, bàn/zone và ngoại lệ nhóm hai người với TA vẫn cần hoàn tất trước khi nộp, không cản trở dựng prototype.

## 1. Duy đã làm những gì?

Phần của Duy đã được soạn và rà soát với sự hỗ trợ của Codex. Duy cần đọc, hiểu và giải thích được phần đứng tên khi demo. Bảng dưới ghi kết quả tài liệu, không khẳng định đã chạy một sản phẩm.

| Phần | Nội dung đã hoàn thành | Bảo sử dụng để làm gì? |
|---|---|---|
| Đọc đề và lập kế hoạch | Đọc yêu cầu chung, T2, mẫu spec, rubric; chốt phạm vi trợ lý học bài tối muộn. | Giữ prototype đúng lát cắt, không mở rộng thành nền tảng học tập tổng quát. |
| §1 | Lát cắt, 3 việc không làm, bảng nguồn, thời gian mô phỏng. | Dựng thông tin nền, trạng thái bài và giới hạn tính năng. |
| §2 | 10 kịch bản S01–S10 phủ 4 lớp rủi ro; chọn S01/S02; thêm N01 bình thường. | Chọn ca demo và đối chiếu hành vi cần xử lý. Không bắt buộc dựng 10 màn hình riêng. |
| §3 | Lời AI nguyên văn cho hai ca khó, nội dung giao diện, đường sửa và chuyển TA, ba nguyên tắc HAX/PAIR. | Lấy câu chữ và hành vi để dựng hai màn hình. |
| §3.5–§3.6 | Phân loại lỗi, cách đính chính và thông báo theo trạng thái gửi. | Tránh báo “đã gửi” khi chỉ có nháp hoặc thao tác thất bại. |
| §4 | Quyền bốn tool, chi phí sai/chờ, người duyệt, trường hợp không duyệt, thử logic trên S01/S02/N01. | Cài đặt đúng quyền, không tự mở thêm hành động. |
| §4.3 | Ghi cả Duy và Bảo chọn phương án 3; giữ phân tích các phương án đã loại. | Dựng gợi ý có giới hạn và chứng minh chặn yêu cầu giải hộ. |
| Thông tin nhóm | Điền tên, mã học viên, email, GitHub hai thành viên. | Giữ nguyên thông tin thật, bổ sung các trường còn thiếu. |
| Bàn giao và kiểm tra | Đối chiếu R1–R4, soạn H1–H3 và checklist C01–C12. | Chạy kiểm tra thật, ghi kết quả và chụp bằng chứng sau khi dựng. |

## 2. Những thay đổi đã chốt trong quá trình làm

| Thay đổi | Kết quả hiện tại |
|---|---|
| Phân công ban đầu chia màn hình cho mỗi người | Đổi thành Duy sở hữu §1–§4; Bảo sở hữu toàn bộ prototype và §5–§7. |
| Ý kiến tool khó nhất còn để trống/chờ Bảo | Đã cập nhật: cả hai chọn phương án 3, Bảo đã xác nhận. Không ghi bất đồng giả. |
| S05 từng gắn mức “sửa được” | Đổi sang “nhẹ” nếu chỉ hiểu nhầm thuật ngữ và sửa ngay bằng một câu hỏi lại, chưa gây sai quyết định bài làm. |
| UX mới chủ yếu mô tả luồng thành công | Bổ sung sửa AI, đổi bài, nháp, đang gửi, gửi lỗi, bổ sung sau gửi và ngoài giờ TA. |
| Chưa rõ xác nhận gắn với bản nội dung nào | Sửa nội dung sau xem trước phải duyệt lại; xác nhận cũ không cho phép gửi nội dung mới. |
| Chưa tách rõ nguồn thật và ví dụ kiểm tra | Phản ví dụ phương sai 0,25 → độ lệch chuẩn 0,5 được ghi riêng là ví dụ nhóm dựng, không giả nguồn khóa học. |
| Có nguy cơ hiểu bảng thử là kết quả chạy | Đã ghi rõ §4.4 là kiểm logic trên giấy; Bảo phải chạy prototype mới được ghi Pass. |
| Cách tích hợp AI | Bản cơ sở mô phỏng HTML/CSS/JS, không API/backend. AI thật là tùy chọn sau, không cản hoàn thành bài chính. |

## 3. File Bảo cần nhận và thứ tự đọc

1. [spec.md](spec.md): nội dung chính §1–§4, đọc trước khi dựng.
2. [HANDOFF.md](HANDOFF.md): file này, dùng làm checklist thực hiện.
3. [REVIEW.md](REVIEW.md): các quyết định, đối chiếu rubric và thông tin chưa hoàn tất.
4. Repo đề: `tracks/t2-education.md`, `03-spec-template.md`, `04-rubric.md`; giữ quyền đọc để đối chiếu fixture và yêu cầu chấm. Bảo không cần chép toàn bộ đề vào repo nộp.

Gửi cho Bảo **cả thư mục `submission-draft/`**, kèm đường dẫn repo đề. Các link tương đối giữa ba file sẽ hoạt động khi giữ chúng trong cùng thư mục. Kế hoạch trong `docs/superpowers/plans/` là tài liệu tham khảo nội bộ, không bắt buộc nộp.

## 4. Bảo cần duyệt gì trước khi dựng?

Việc Bảo đã chọn phương án 3 được ghi nhận; các mục sau là xác nhận cách chuyển thiết kế thành prototype, không phải yêu cầu chọn lại phương án.

- [ ] Đọc §1–§4 và xác nhận hiểu đúng hai ca S01/S02 cùng N01; báo lại Duy nếu có câu chữ khó triển khai.
- [ ] Kiểm tra lời AI có thể dùng nguyên văn; nếu rút ngắn, phải giữ nguồn, giới hạn, bước tiếp và trạng thái TA ngoài giờ.
- [ ] Xác nhận hai góc nhìn học viên/TA là mô phỏng; không trình bày như đã có hệ thống TA thật.
- [ ] Rà khả năng dựng các trạng thái ở §3.6 và luật §4.7. Phần nào chưa làm được thì báo trước, cùng thu hẹp phạm vi và ghi giới hạn; không âm thầm bỏ.
- [ ] Chọn cách bố trí và công cụ; mặc định HTML/CSS/JS thuần. Có thể đổi công cụ nhưng giữ các hành vi và số màn hình theo đề.
- [ ] Cùng Duy chốt tên nhóm, lớp, bàn/zone và xác nhận ngoại lệ hai người với TA trước khi nộp. Không tự ghi đã được miễn.

## 5. Thứ tự Bảo thực hiện

| Bước | Việc cần làm | Kết quả cần có |
|---|---|---|
| B1 — Chuẩn bị | Tạo repo nộp mới khi hai người chốt tên; hoặc dựng trong thư mục làm việc riêng trước. Mang `spec.md` sang, giữ nguyên §1–§4. | Khung bài tách khỏi repo đề; không công khai/push từ phiên Codex hiện tại khi Duy chưa duyệt. |
| B2 — Nạp fixture | Chép đúng tài liệu, lịch bài và giờ TA từ T2; gắn đồng hồ mô phỏng. | Nguồn có mã, bài mở/đóng rõ, không phụ thuộc giờ máy. |
| B3 — Luồng S01 | Dựng xem nguồn → cảnh báo sai → sửa/bỏ báo cáo → duyệt gửi → hàng chờ. | Bấm hết ca tài liệu sai, cùng mã/nội dung giữa hai màn hình. |
| B4 — Luồng S02 | Dựng hỏi giải hộ → giới hạn → gợi ý bước đầu; thử xin xác nhận và yêu cầu lặp. | Không lộ đáp số hoặc nhận xét hộ; không tự gửi TA. |
| B5 — Đường bổ sung | Thêm N01, S05, sửa AI/đổi bài, lỗi gửi/thử lại, FAQ cần TA duyệt. | Có đường bình thường, mơ hồ, thất bại và sửa lỗi; thấy ít nhất hai mức tự chủ. |
| B6 — Kiểm tra | Chạy C01–C12 ở phần dưới; sửa lỗi và lưu kết quả thật. | Nhật ký Pass/Fail, lỗi còn lại; không đánh dấu trước khi chạy. |
| B7 — Bằng chứng | Chụp 1–2 ảnh đánh số H1–H3, viết README mở/chạy và phần mock. | Người khác tự mở được và chỉ được nguyên tắc trên ảnh/màn hình. |
| B8 — Viết §5–§7 | Bổ sung nội dung theo yêu cầu bên dưới. | Spec đầy đủ; phần chưa demo được ghi chưa diễn ra. |
| B9 — Trả Duy duyệt | Gửi link/file mở được, spec đã ghép, ảnh, kết quả kiểm tra và danh sách thay đổi. | Duy đối chiếu thiết kế; thống nhất sửa trước khi commit/nộp. |

## 6. Bảo cần viết gì ở §5–§7?

### §5 — Prototype

- File/link và cách mở; công cụ; phần nào mock; có hay không lời gọi AI thật.
- 1–2 ảnh thực tế, đánh số H1–H3: mỗi số trỏ nguyên tắc, hành vi và mức tự chủ tương ứng.
- Lập luận chọn cách hiện nguồn, sự không chắc và bước duyệt; nêu cách hiển thị khác đã cân nhắc và vì sao loại.
- Giới hạn thật, chẳng hạn chỉ xử lý ca chọn sẵn hoặc chưa hỗ trợ bổ sung ticket. Không mô tả tính năng chưa dựng là đã có.

### §6 — Tốt là gì

Bảo chốt ba tiêu chí Pass/Fail chấm được. Có thể dùng ba tiêu chí gợi ý sau sau khi đối chiếu sản phẩm:

1. Với S02, không lộ/xác nhận đáp số và nhận xét hộ qua tin nhắn, gợi ý lặp hoặc FAQ.
2. Với S01/S02, xem được nguồn đúng; phần nghi sai và ví dụ nhóm dựng được phân biệt; không bịa nguồn.
3. Với S01/S02, chỉ báo vào hàng chờ sau thao tác thành công đã duyệt; chưa gửi/gửi lỗi không tạo thông báo thành công; FAQ không tự xuất bản.

Chấm từng tiêu chí trên cả S01 và S02; nếu một tiêu chí không bị kích hoạt trong một ca, ghi cách kiểm hoặc “không áp dụng” cùng lý do, không tự đánh Pass. Ghi lỗi còn lại và ảnh hưởng. Bảng kiểm C01–C12 giúp có bằng chứng, không thay thế ba tiêu chí này.

### §7 — Demo

- Chuẩn bị đường demo khoảng 4 phút, phân lời cho cả Duy và Bảo; Duy giải thích thiết kế, Bảo bấm và chỉ nguyên tắc/quyền.
- Thử trước một ca lạ ngoài hai ca chính; không dùng lần tập làm như ca đã nhận từ TA.
- Sau demo ghi đúng ca lạ thực tế, prototype phản ứng thế nào và có đổi thiết kế không. Trước demo ghi “chưa diễn ra”.

Khi ghép bản cuối, thay ghi chú ở đầu spec bằng trạng thái đúng thực tế. Chỉ bỏ nhãn “chưa có prototype” sau khi đã dựng; các vị trí H1–H3 phải được nối với ảnh thật. Không xóa các giới hạn còn tồn tại để làm bài trông hoàn chỉnh.

## Phạm vi B nhận

- Dựng hai màn hình: trợ lý học viên và hàng chờ TA mô phỏng.
- Viết §5–§7 dựa trên sản phẩm thực tế; không sao chép bảng thử trên giấy thành kết quả đã chạy.
- Giữ thời gian cố định 22:30 ngày 13/11/2026 và nhãn mô phỏng. Không cần backend/API cho bản cơ sở.
- Dùng fixture nguyên văn từ `tracks/t2-education.md` trong repo đề khi dựng. Khi nộp repo mới, không để link đọc tài liệu phụ thuộc một đường dẫn trong repo đề đã bị bỏ.

## Hợp đồng hành vi

| Nội dung | Nguồn quyết định | B phải thể hiện |
|---|---|---|
| S01 — tài liệu sai | §2.1, §3.1 | Đúng trích đoạn, phản ví dụ có nhãn riêng; sửa/bỏ báo cáo; xác nhận gửi; hàng chờ nhận cùng nội dung. |
| S02 — bài mở | §2.1, §3.2 | Hạn nộp và nguồn; chỉ bước đầu; chặn xin đáp số, xác nhận kết quả và gợi ý liên tiếp thành lời giải. |
| N01 — câu bình thường | §2.1, §4.4 | Giải thích trung bình/trung vị có nguồn ngay; không yêu cầu gửi TA. |
| S05 — mơ hồ | §2.1, §3.4 | Một câu hỏi làm rõ trước khi giải thích. |
| Người học sửa AI | §3.5 | Hiện đính chính, không âm thầm xóa sai; đổi bài thì đánh giá lại quyền. |
| Chuyển TA | §3.6, §4.2 | Xem bản nháp → sửa/bỏ → duyệt → kết quả gửi; ngoài giờ và chưa đọc hiển thị rõ. |
| FAQ | §4.1–§4.2 | Chỉ TA duyệt; bài mở và nguồn sai chưa xác minh không được đăng như kiến thức chính thức. |

## Hai màn hình — phác bố cục để triển khai

```text
HỌC VIÊN
[Trợ lý AI] [Dữ liệu và thời gian mô phỏng]
[Bài 3 đang mở · hạn 23:59] [TA ngoài giờ]
Tin người học → phản hồi AI
H1: Nguồn và phần cần kiểm tra [Xem nguồn]
H2: Câu hỏi/bản nháp [Sửa] [Bỏ trước gửi]
H3: Giới hạn, người nhận, thời gian [Xem trước] [Xác nhận gửi]
Kết quả: đang gửi / lỗi / mã yêu cầu đã vào hàng chờ

TA — GÓC NHÌN MÔ PHỎNG
[Hàng chờ] → yêu cầu với cùng mã và nội dung học viên đã duyệt
[Nguồn] [Trạng thái bài] [Cờ nghi vấn]
[Đánh dấu đã xem] [Xem dự thảo FAQ]
[Duyệt đăng] chỉ khi đủ nguồn và không chứa lời giải bài mở
```

Đây là phác thảo đề xuất, B được đổi cách bố trí. Giữ nguyên ý nghĩa H1–H3 và dùng cùng mã trên ảnh §5. Nút H2 phải cho sửa thật, không chỉ là nhãn trang trí. Hiện nguồn thay vì phần trăm tin cậy không có căn cứ.

## Dữ liệu và trạng thái tối thiểu

- Kịch bản: `id`, `message`, `sourceIds`, `exerciseStatus`, `riskClass`, `expectedAction`.
- Yêu cầu: `id`, `scenarioId`, `summary`, `sourceIds`, `status`; nội dung tạo từ bản học viên vừa xác nhận.
- Yêu cầu: `draft → queued → reviewed`. “Đang gửi”, “gửi lỗi”, “chưa rõ kết quả” là trạng thái hiển thị cần phân biệt, không tự tạo thành công.
- FAQ: `draft → published` sau TA duyệt và vượt kiểm tra nội dung.
- Không đổi nội dung yêu cầu đã gửi tại chỗ. Nếu hỗ trợ bổ sung: bản nháp mới liên kết yêu cầu gốc, duyệt gửi riêng; ghi rõ luật bổ sung.
- Đổi tab giữ dữ liệu; reset xóa trạng thái mô phỏng và đưa về đầu ca. Không reset giữa luồng để làm như demo đi hết tự nhiên.

## Checklist B chạy và ghi kết quả thực tế

| Mã kiểm | Thao tác | Kỳ vọng |
|---|---|---|
| C01 | Bấm hết S01, xem nguồn rồi sửa báo cáo | Trích đúng §3.3; phản ví dụ không bị gắn nhãn nguồn khóa học; bản nháp sửa được. |
| C02 | Bỏ bản nháp S01 | Không có yêu cầu mới trong hàng chờ. |
| C03 | Gửi S01 thành công | Hàng chờ có đúng nội dung đã duyệt; hiện chưa đọc và ngoài giờ, không hứa trước hạn. |
| C04 | Gửi thất bại rồi thử lại | Giữ nháp, không báo đã gửi sai; thử lại thành công không tạo trùng. |
| C05 | Gửi lặp hoặc đổi tab khi đang gửi | Không gửi trùng, không mất kết quả; chưa rõ kết quả phải báo đúng. |
| C06 | Sửa nội dung sau khi xem trước | Xem/duyệt lại bản mới, không dùng đồng ý cũ. |
| C07 | Xin giải S02 rồi xin xác nhận đáp số | Không có đáp số hoặc nhận xét hộ trong tin nhắn, thẻ nguồn phụ, FAQ hay phản hồi xác nhận. |
| C08 | Xin thêm từng bước liên tiếp | Không ghép thành toàn bộ lời giải; vẫn xem được khái niệm có nguồn. |
| C09 | Đổi câu hỏi từ bài 2 sang bài 3 | Đánh giá lại trạng thái; quyền giải bài đã đóng không áp dụng cho bài mở. |
| C10 | Người học yêu cầu tự đăng FAQ | Không được xuất bản; chuyển góc nhìn TA cũng không vượt chặn nội dung bài mở. |
| C11 | Hỏi N01 và S05 | N01 trả lời ngay có nguồn; S05 hỏi làm rõ, không đoán. |
| C12 | Nhập ca lạ/nguồn không có như “slide 12” | Không bịa; nói giới hạn hoặc hỏi lại. Nếu chỉ hỗ trợ ca chọn sẵn, công bố giới hạn thay vì giả chatbot tổng quát. |

Không đánh dấu Pass trước khi thao tác thực tế. B ghi Pass/Fail và lỗi còn lại trong tài liệu kiểm tra của mình; §6 do B chọn ba tiêu chí rõ từ hành vi đã dựng.

## Mốc trả lại A

1. Có bản bấm được: A đối chiếu lời AI, nút và quyền với §3–§4.
2. Có hai ảnh H1–H3: kiểm đúng vị trí nguyên tắc, đủ hai mức tự chủ.
3. Có kết quả chạy: bổ sung giới hạn còn lại, thống nhất nội dung §5–§7.

Thành viên B được tùy chọn cách trình bày và tổ chức mã. Thay nguồn, mức tự chủ, lời hứa thời gian hoặc ranh giới bài mở cần đưa về A để duyệt lại.

## 7. Điều kiện bàn giao ngược và chốt bài

Bảo gửi lại cho Duy một bộ gồm:

- [ ] `spec.md` đã có §5–§7, nêu rõ phần demo thực tế chưa xảy ra nếu còn chờ.
- [ ] `prototype/` có mã hoặc README chứa link truy cập được, cách mở, giới hạn mock và ảnh đánh số.
- [ ] Kết quả C01–C12 và bảng ba tiêu chí trên hai ca khó; lỗi chưa sửa được ghi rõ.
- [ ] Danh sách file và hành vi đã đổi so với §1–§4; Duy duyệt thay đổi thiết kế trước khi chốt.
- [ ] Thông tin nhóm đầy đủ và trạng thái ngoại lệ TA đúng thực tế; kiểm repo công khai mở ẩn danh trước khi nộp.

**Quy tắc commit trong công việc Codex hiện tại:** Duy kiểm tra kết quả rồi đồng ý rõ ràng mới commit; chưa có commit/push từ phần việc này. Tài liệu bàn giao đã đủ để Bảo bắt đầu triển khai, còn bài nộp cuối chỉ hoàn tất sau khi ghép prototype, bằng chứng và các thông tin thật còn thiếu.
