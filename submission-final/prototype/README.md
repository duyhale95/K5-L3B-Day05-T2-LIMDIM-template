# Prototype — Trợ lý học bài tối muộn (T2 Giáo dục)

**Mở:** tải thư mục này về rồi mở `index.html` bằng Chrome, Edge hoặc Firefox. Không cần cài đặt, không cần mạng, không cần đăng nhập hay API key.

| Thứ | Giá trị |
|---|---|
| Công cụ | HTML/CSS/JavaScript thuần, một file `index.html` |
| Số màn hình | 2: **Màn 1 · Học viên** và **Màn 2 · Hàng chờ TA (mô phỏng)**, chuyển bằng tab |
| Lời gọi AI thật | **Không có.** Câu trả lời do luật từ khoá chọn ra, câu chữ lấy từ `spec.md` §3 |
| Phần mock | Câu trả lời của AI, hàng chờ TA, FAQ, mã yêu cầu `YC-…`, lỗi mạng (bật trong "Bảng điều khiển demo"). Đồng hồ cố định ở **22:30 ngày 13/11/2026**, không lấy giờ máy |
| Dữ liệu | Chỉ dùng dữ liệu dựng trong `tracks/t2-education.md`: tài liệu buổi 3 §3.1–§3.5 và trang khóa học. Không có dữ liệu thật |

## Bấm thử ca khó trong khoảng 4 phút

1. **S01 · Tài liệu §3.3 sai.** Bấm tin mẫu *S01 · Tài liệu §3.3*, rồi bấm thẻ **§3.3 ⚠** để xem câu nguồn được tô vàng (H1). Ví dụ kiểm tra 0,25 → 0,5 nằm trong khung riêng có nhãn "do nhóm dựng".
   - Bấm **Soạn báo cáo cho TA**, sửa nội dung (H2), bấm **Xem trước**. Màn hình hiện người nhận, giờ TA và dòng "không cam kết trước hạn" (H3).
   - Bấm **Xác nhận gửi TA**. Trạng thái đi qua "Đang gửi" rồi "Đã vào hàng chờ · YC-101 · TA chưa đọc".
2. Chuyển sang **Màn 2**. Yêu cầu YC-101 có đúng nội dung học viên đã duyệt. Bấm **Nhờ AI soạn dự thảo FAQ**, rồi **Duyệt đăng FAQ**: hệ thống chặn vì TA chưa tích ô kiểm tra và chưa xem yêu cầu gốc (H5). Bấm **Đánh dấu đã xem**, tích ô kiểm tra, duyệt lại thì mới đăng được.
3. **S02 · Xin giải bài 3.** Trợ lý chỉ đưa bước đầu.
   - **S03 · Xác nhận đáp số**: bị từ chối, kể cả khi học viên chỉ hỏi "đúng hay sai".
   - **Xin thêm bước**: bị chặn, vẫn có ví dụ khác để học khái niệm.
   - Không có nút "Xem đáp án" (H3b).
4. **Correction (người dùng sửa AI).** Mở *Bảng điều khiển demo*, bật "AI lặp câu sai §3.3", bấm S01, rồi bấm *Phản bác*. Câu sai cũ được giữ lại, gạch ngang, có nhãn đính chính.
5. **Ca lạ.** Gõ tự do vào ô chat, ví dụ "slide 12", "p-value", "hệ số tương quan". Câu nào không có trong tài liệu thì trợ lý nói thẳng là không có và đề nghị soạn câu hỏi cho TA.

Muốn quay lại từ đầu thì bấm **Reset về đầu ca** trong Bảng điều khiển demo.

## Ảnh đánh số

Bật chú thích bằng ô "Hiện số chú thích" trong Bảng điều khiển demo, hoặc mở `index.html?annot=1`. Ảnh được chụp tự động từ các cảnh dựng sẵn `?scene=s01|s02|ta&annot=1`.

| Ảnh | Cảnh |
|---|---|
| `anh-s01.png` | S01: nguồn §3.3 có câu cần kiểm tra (H1), nhãn độ chắc (H4), bản nháp báo cáo sửa/bỏ được (H2) |
| `anh-s02.png` | S02 + S03: giới hạn bài đang mở (H4), không có nút làm việc cấm (H3b), xem trước và duyệt gửi TA ngoài giờ (H3) |
| `anh-ta.png` | Màn TA: hàng chờ nhận đúng nội dung đã duyệt, FAQ bị chặn khi chưa có TA kiểm (H5) |

Bảng giải thích từng số nằm ở `spec.md` §5.2.

## Tự kiểm C01–C12

Mở `index.html?selftest=1`. Trang sẽ tự bấm qua checklist C01–C12, cộng thêm X1–X5, rồi in kết quả ở cuối trang. Kết quả chạy bằng Chrome headless lưu ở `selftest-result.txt`: **17/17 PASS**. X4 kiểm FAQ của S01 chỉ đăng được sau khi TA duyệt; X5 kiểm lời giới hạn không mở thêm quyền.

Bộ test này bấm vào giao diện thật của prototype. Nó **không** chứng minh một chatbot tổng quát đã an toàn: bộ luật chỉ phủ các ca trong `spec.md` §2, và câu chưa có luật sẽ rơi về nhánh "tài liệu không có".
