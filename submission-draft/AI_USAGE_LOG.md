# Nhật ký sử dụng AI — LAB5 T2 · Nhóm LIMDIM

File này ghi việc sử dụng AI để hỗ trợ làm bài. Đây không phải log gọi mô hình từ prototype và không phải bằng chứng nhận bonus lời gọi AI thật.

## Phạm vi và nguồn xác nhận

- Công cụ trong phiên làm việc với Hà Lê Duy: Codex. Không ghi phiên bản mô hình vì chưa có thông tin xác nhận.
- Căn cứ: yêu cầu và xác nhận trong chat của Duy; các file và commit hiện có trong repo.
- Không có toàn bộ lịch sử công cụ riêng của Nguyễn Thiên Bảo. Không suy đoán Bảo đã dùng công cụ AI nào để dựng prototype.
- Các mốc dưới đây ghi theo thứ tự công việc, không dựng giờ bắt đầu/kết thúc hoặc số lượt prompt.

## Nhật ký công việc có thể xác nhận

| Mốc | Yêu cầu / đầu vào | Codex hỗ trợ | Quyết định hoặc kiểm tra của con người | Bằng chứng |
|---|---|---|---|---|
| 1. Hiểu đề | Duy yêu cầu đọc lab và dùng skill | Đọc tài liệu chung, các track, hướng dẫn và rubric; tóm tắt bài toán | Duy chọn T2 | Nội dung tài liệu đề và lịch sử chat |
| 2. Lập kế hoạch | T2, nhóm hai người | Đề xuất hai ca tài liệu sai/bài đang mở; kế hoạch và phương án chia việc | Duy đổi phân công: nhận §1–§4; Bảo nhận prototype và §5–§7; Duy duyệt kế hoạch | `docs/superpowers/plans/2026-11-13-track2-lab-plan.md` |
| 3. Soạn nội dung | Fixture T2, mẫu spec, R1–R4 | Soạn 10 kịch bản, lời AI, UX lỗi, ma trận tool, phản ví dụ toán học và bàn giao | Duy xem, yêu cầu hoàn thiện, cung cấp thông tin thành viên | `submission-draft/spec.md`, `REVIEW.md`, `HANDOFF.md` |
| 4. Ghi nhận lựa chọn | Duy cho biết cả hai chọn phương án 3, Bảo đã xác nhận | Cập nhật §4.3 theo xác nhận; bỏ đoạn phản biện còn là giả định | Duy xác nhận lựa chọn của hai thành viên; không dựng bất đồng | `spec.md` §4.3 và lịch sử chat |
| 5. Lưu trên GitHub | Duy yêu cầu commit rõ ràng và push main | Kiểm tra Git, commit 4 file tài liệu, push `main` | Duy cho phép commit/push rõ ràng | Commit `5529b08` — `docs(t2): complete sections 1-4 and handoff to Bao` |
| 6. Nhận bản prototype | Commit mới từ remote | Pull fast-forward từ `5529b08` tới `e6a9dcb`; đọc prototype, ảnh, log và §5–§7 | Chưa có xác nhận cuối của Duy về bản mới trong lượt kiểm tra này | Commit `e6a9dcb` — `feat(t2): add prototype, screenshots, self-test and spec sections 5-7` |
| 7. Rà lại bài | Duy yêu cầu humanize, log AI và kiểm tra trạng thái nộp | Dùng humanize-text để rà câu chữ; đọc đối chiếu spec/mã; chạy lại self-test trên Chrome headless | Duy sẽ duyệt kế hoạch chỉnh sửa trước khi thực hiện | Self-test trong lượt này: `SELFTEST 15/15`, các ca C01–C12 và X1–X3 đều PASS |

## Những gì AI chưa làm hoặc chưa xác nhận

**Cập nhật sau khi Duy duyệt kế hoạch rà bài:** Codex đã chỉnh lời giới hạn, FAQ S01, tiêu chí nguồn và kết luận về rò đáp án; đồng bộ tài liệu và chụp lại ba cảnh. Hai kiểm tra X4/X5 thất bại trước sửa; sau sửa, `SELFTEST 17/17` PASS, log ở `prototype/selftest-result.txt`. Duy sẽ kiểm kết quả trước commit/push. Chưa có thông tin mới xác nhận demo hoặc nộp bài.

- Không gọi mô hình AI thật từ prototype: `prototype/index.html` dùng câu trả lời và luật từ khóa viết sẵn. “AI đã hỗ trợ làm bài” không có nghĩa sản phẩm có lời gọi AI thật.
- Không xác nhận bài đã được nộp qua kênh giảng viên. Repo có trên GitHub chỉ chứng minh đã lưu/push mã và tài liệu.
- Không có bằng chứng trong repo rằng demo đã diễn ra; §7 hiện vẫn ghi chưa diễn ra. Điều này không tự chứng minh chưa nộp bài.
- Không tự tạo xác nhận của TA hay ban tổ chức. Bản mới ghi ban tổ chức cho nhóm 2–4 người; nguồn thông báo này cần nhóm đối chiếu trước khi nộp.
- Chưa kiểm chứng toàn bộ cách diễn đạt tự do hoặc an toàn của một mô hình ngôn ngữ thật. Self-test chỉ phủ các ca đã lập trình.

## Trách nhiệm của nhóm trước khi nộp

**Chỉnh biên tập theo góp ý Argon:** Theo yêu cầu của Duy, đã bỏ dẫn chiếu log này khỏi `spec.md` và `prototype/README.md`, rút gọn phần lựa chọn của hai thành viên và thay lời nhắc Bảo bằng mô tả thiết kế đã dựng. Log vẫn được giữ riêng; thông tin prototype không gọi mô hình thật vẫn có ở §5.1 và README. Không bổ sung giả định rằng hai người chọn độc lập ngay từ đầu, không tạo kết quả demo hoặc số bàn khi chưa có dữ liệu.

Duy và Bảo kiểm tra lại nội dung đứng tên, giải thích được quyết định thiết kế và xác nhận kết quả demo/nộp bài bằng thông tin thực tế. Nếu Bảo có dùng AI trong quá trình dựng, Bảo bổ sung tên công cụ, phần đã dùng, cách kiểm tra và bằng chứng có thật vào log này. Không bổ sung prompt hoặc kết quả không còn nguồn xác nhận.
