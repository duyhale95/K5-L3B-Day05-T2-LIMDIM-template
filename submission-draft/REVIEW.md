# Phiếu kiểm tra bài T2 sau khi nhận prototype

## Trạng thái hiện tại — kết quả để Duy kiểm tra

**Cập nhật theo góp ý Argon:** đã bỏ dẫn chiếu AI Log khỏi hai file bài nộp, giữ nhật ký riêng; rút gọn §4.3 thành lựa chọn chung Duy/Bảo; thay lời nhắc Bảo bằng trạng thái đã dựng và tham chiếu C04/C10/X4. §7 chuyển sang kế hoạch demo và ô ghi nhận sau demo. Không điền giả bàn/zone, không thêm lịch sử “chọn độc lập ngay từ đầu”. Các đoạn bên dưới ghi việc rà trước lượt biên tập này; dẫn chiếu AI Log từng thêm vào spec/README đã được gỡ theo yêu cầu mới.

- Đã nhận prototype và §5–§7 từ commit `e6a9dcb` của Bảo.
- Đã chỉnh lời giới hạn trên UI để nói rõ việc học viên có thể làm tiếp, thay cho câu mô tả “không có nút”. Không đổi mức tự chủ đã chốt.
- Sửa FAQ S01: không nhận giảng viên đang xem lại khi chưa có căn cứ; ghi đúng khoảng `0 < phương sai < 1` và trường hợp bằng nhau tại 0/1; tách phép kiểm của nhóm khỏi trích nguồn.
- Sửa tiêu chí nguồn T2 để dùng được cả tài liệu A lẫn trang khóa học B; câu “không có slide 12” không bị coi là bịa nguồn.
- Bỏ khẳng định không thể rò đáp án chỉ vì prototype không tính bài 3; giữ giới hạn bộ chặn FAQ và trách nhiệm TA kiểm tra.
- Bỏ phỏng đoán về phần trăm tin cậy; phần minh bạch AI ở H0 chỉ gắn G1, không cần khẳng định pháp lý ngoài phạm vi bài.
- Đã chạy lại Chrome headless: **17/17 PASS**. X4/X5 đã thất bại trước sửa, rồi đạt sau sửa. X5 được sửa cách quan sát cho đúng UI: đọc lời giới hạn sau từng câu hỏi vì trang chỉ hiện phần này ở tin mới nhất.
- Đã chụp lại và xem ba ảnh; hai ảnh học viên là ảnh chính, ảnh TA là bổ sung. Nhãn H3b về “việc cấm” chỉ thuộc chế độ chú thích demo.
- [AI_USAGE_LOG.md](AI_USAGE_LOG.md) đã được liên kết từ spec và README prototype. Không biết công cụ AI riêng Bảo dùng; không ghi thay.
- Chưa commit/push lượt sửa này. Chưa xác nhận demo/nộp qua kênh lớp; bàn/zone vẫn chưa điền. Quy định nhóm 2–4 người là thông tin trong bản Bảo bổ sung, nhóm cần giữ nguồn thông báo thật.

## Phương án cấu trúc repo cuối — đề xuất, chưa di chuyển hoặc xóa

```text
spec.md
AI_USAGE_LOG.md
README.md                 ← cách mở prototype, thành viên, link spec, trạng thái demo/nộp thật
prototype/
  index.html
  README.md
  selftest-result.txt
  anh-s01.png
  anh-s02.png
  anh-ta.png
```

Đề xuất đưa bài từ `submission-draft/` ra root; chuyển tài liệu đề, kế hoạch và bàn giao nội bộ sang bản lưu cục bộ ngoài repo trước khi bỏ chúng khỏi cây bài nộp. Không sửa lịch sử Git hoặc xóa bản tham chiếu duy nhất. Cần Duy đồng ý riêng với thao tác dọn repo; hiện chưa thực hiện. Cấu trúc Git hiện tại kế thừa repo đề nên chưa đáp ứng yêu cầu “repo mới, không clone rồi push”; dọn file chỉ sửa cây hiện tại, không biến lịch sử thành repo mới. Nếu cần tuân thủ đầy đủ, nhóm phải chọn repo mới trống chứa đúng bộ bài rồi nộp link mới.

## Phạm vi kiểm chứng

Đã kiểm ca viết sẵn và ảnh của prototype. Chưa đánh giá một mô hình thật, mọi đầu vào tự do hoặc việc nộp bài ở hệ thống ngoài GitHub. Chưa thể tuyên bố toàn bộ bài đạt tuyệt đối hoặc đã được giảng viên chấp nhận.

---

## Bản rà §1–§4 trước khi có prototype — giữ làm lịch sử

Các trạng thái “chưa có màn hình/chưa chạy” trong phần bên dưới là ghi nhận ở mốc bàn giao ban đầu, không phải trạng thái hiện tại.

**Trạng thái:** đã hoàn thiện nội dung theo kế hoạch được duyệt; chờ người dùng kiểm tra kết quả. Chưa stage, commit, push hoặc tạo repo nộp.

## File được tạo

- `spec.md`: nội dung §1–§4, bảng phân công hai thành viên, nguồn dữ liệu, 10 ca rủi ro, ca bình thường, hai luồng UX chi tiết, ba nguyên tắc HAX/PAIR và ma trận bốn tool.
- `REVIEW.md`: phạm vi thay đổi và điểm cần duyệt.
- `HANDOFF.md`: bản bàn giao cho B, bố cục dự kiến, trạng thái và 12 ca kiểm tương tác để B chạy sau khi dựng.

## Thay đổi trong lượt hoàn thiện

- Điền họ tên, mã học viên, email và GitHub của Hà Lê Duy (A), Nguyễn Thiên Bảo (B) theo thông tin người dùng cung cấp.
- Hoàn tất §4.3 theo xác nhận của Duy: Duy và Bảo đều chọn phương án 3, Bảo đã xác nhận; không có bất đồng về mức tự chủ. Giữ phân tích các phương án và yêu cầu kiểm chứng trên prototype.
- Điều chỉnh S05 thành mức nhẹ với điều kiện chỉ hiểu nhầm thuật ngữ, chưa dẫn tới sai quyết định bài làm.

- Bổ sung §3.5: phân biệt lỗi hệ thống, nhập nhầm của người học và lỗi ngữ cảnh; mỗi loại có lời AI và cách sửa riêng.
- Bổ sung §3.6: câu chữ cho bản nháp, đang gửi, thành công, thất bại, hủy trước gửi và bổ sung sau gửi.
- Bổ sung §4.7: duyệt đúng nội dung mới nhất, chống gửi trùng, đánh giá lại quyền khi đổi bài, không sửa lịch sử đã gửi hoặc hứa hoàn tác giả.
- Làm rõ bằng chứng S08: tài liệu không có dữ liệu đánh giá năng lực, tool không có quyền gắn nhãn người học.
- Tách bàn giao kỹ thuật khỏi bài nộp để B triển khai mà không kéo chi tiết kỹ thuật vào lời nói với học viên.

## Đối chiếu R1–R4 (65 điểm trọng số, không tự chấm điểm)

| Tiêu chí | Bằng chứng trong spec | Trạng thái |
|---|---|---|
| R1: đúng lát cắt, 3 giới hạn có lý do | §1.1–§1.2 | Có nội dung; cần đối chiếu prototype sau. |
| R2: ≥8 ca phủ 4 lớp | §2.1, S01–S10 | Có 10 ca và N01 để đối chứng. |
| R2: lỗi có tool/dữ liệu, hành vi tốt, mức hại | Các cột bảng §2.1 | Có; mức hại là lập luận thiết kế. |
| R2: hai ca ưu tiên và ca suýt chọn | §2.2 | Có S01/S02, so với S03/S10. |
| R3: lời AI, màn hình, bước tiếp, người nhận | §3.1–§3.2, §3.6 | Có; chưa có bằng chứng màn hình. |
| R3: phương án chọn/loại | §3.1–§3.2 | Có lập luận cho từng ca. |
| R3: 2–3 nguyên tắc chỉ được vị trí | §3.3, H1–H3 | Có đặc tả; B phải thay bằng ảnh thật ở §5. |
| R3: phân loại lỗi và cách sửa | §3.5 | Có ba loại với tình huống và lời nói khác nhau. |
| R3: lỗi câu chữ không cứu được | Cuối §3.1, §3.2; §4.7 | Có chặn FAQ và chặn đáp án trước hiển thị. |
| R4: mức cho tất cả tool | §4.1 | Đủ 4 tool; luật cấm ghi rõ ở §4.2. |
| R4: hậu quả, đảo lại, cái giá chờ, phương án loại | Bốn hàng §4.1 | Có cho từng tool. |
| R4: tool khó nhất, cân nhắc và chốt | §4.3 | Đã ghi lựa chọn của cả A/B và cách chốt phương án 3 theo thông tin Duy xác nhận. Có phân tích đánh đổi; triển khai cần kiểm chứng riêng. |
| R4: thử hai ca khó và một bình thường | §4.4 | Có duyệt logic trên giấy, chưa chạy tương tác. |
| R4: mức tự chủ đổi lời hứa | §4.6 | Có lời hứa sản phẩm nguyên văn. |

**Giới hạn của lần kiểm tra này:** kiểm nội dung và tính nhất quán bằng cách đọc đối chiếu cùng kiểm cấu trúc văn bản. Không phải chấm điểm chính thức, không có kiểm thử prototype hoặc đánh giá độc lập của TA.

Không sửa tài liệu đề, không dựng prototype hoặc viết thay phần §5–§7 của B. Thư mục này là khu vực bản nháp trong workspace hiện tại; khi nộp cần chuyển bài đã duyệt sang repo mới theo yêu cầu đề.

## Các quyết định cần duyệt

1. Ưu tiên S01 tài liệu sai và S02 xin giải bài đang mở; S10 ngoài giờ/sát hạn là điều kiện bắt buộc của cả hai luồng.
2. `tra_cuu_tai_lieu` và `goi_y_bai_tap` tự làm có giới hạn; `chuyen_TA` cần học viên duyệt; `dang_FAQ` cần TA duyệt. Các hành vi bị cấm không được mở khóa bằng xác nhận của học viên.
3. Hiện phản ví dụ phương sai 0,25 → độ lệch chuẩn 0,5, tách nhãn “ví dụ kiểm tra do nhóm dựng” khỏi nguồn khóa học. Không coi nó là tài liệu do giảng viên cung cấp.
4. Dùng giờ mô phỏng 22:30 ngày 13/11/2026; nói rõ TA ngoài giờ và không cam kết trước hạn.
5. Dùng H1 nguồn, H2 sửa bản nháp và H3 giới hạn/duyệt chuyển làm mã bàn giao cho prototype, chưa gọi là ảnh bằng chứng.

## Những thông tin chưa thể điền thay nhóm

- Tên nhóm, lớp và bàn/zone. Tên, mã học viên, email và GitHub đã được điền.
- TA có đồng ý nhóm hai người không.
- Link prototype, ảnh, kết quả chạy, tiêu chí đánh giá và ca lạ thực tế: B bổ sung ở §5–§7.

## Kiểm tra nội dung trước gửi duyệt

- Đối chiếu với T2, mẫu spec và R1–R4 trong rubric.
- Kiểm số ca, độ phủ lớp rủi ro, đủ bốn tool, ba ca thử mức và mã HAX/PAIR.
- Kiểm không công bố đáp số bài 3, không bịa thảo luận hoặc kết quả prototype.
- Mọi kết quả thử ở §4 đều được ghi là duyệt thiết kế trên giấy; chưa chấm prototype đạt.

Người dùng duyệt nội dung xong mới thực hiện commit theo chỉ dẫn tiếp theo; đồng ý soạn bản nháp không được hiểu là đồng ý commit.
