# Đóng góp cho goodbye-whiteboard-video-vn

Cảm ơn bạn đã muốn đóng góp cho bản tiếng Việt này. Repo này hướng tới người Việt là chính: video dọc 9:16, giọng Việt, làm nhanh, dùng được ngay cho Reels / TikTok.

## Cách đóng góp code / tài liệu

1. **Fork** repo này về tài khoản GitHub của bạn.
2. **Clone** fork của bạn về máy:
   ```bash
   git clone https://github.com/<ten-tai-khoan-cua-ban>/goodbye-whiteboard-video-vn.git
   cd goodbye-whiteboard-video-vn
   ```
3. **Tạo branch mới** từ `main`, đặt tên rõ ràng:
   - Tính năng mới: `feat/<ten-ngan-gon>` — ví dụ `feat/caption-tiktok`
   - Sửa lỗi: `fix/<ten-ngan-gon>` — ví dụ `fix/subtitle-che-hinh`
   - Tài liệu: `docs/<ten-ngan-gon>` — ví dụ `docs/huong-dan-giong`
4. Sửa code / tài liệu trên branch đó. Không sửa trực tiếp trên `main` của bạn rồi gửi PR từ `main`.
5. **Gửi Pull Request (PR)** về repo gốc `ikuraikura003-bot/goodbye-whiteboard-video-vn`, branch `main`. Trong mô tả PR ghi rõ:
   - Thay đổi gì, vì sao cần thay đổi.
   - Đã test như thế nào (xem mục “Test trước khi gửi PR” bên dưới).
   - Ảnh / video kết quả nếu thay đổi ảnh hưởng tới video đầu ra.
6. **Chủ repo sẽ duyệt rồi Merge.** Bạn không tự merge khi chưa được duyệt. Nếu PR cần sửa, chủ repo sẽ bình luận — bạn sửa trên cùng branch đó, PR sẽ tự cập nhật.

## Cách báo lỗi / gợi ý tính năng

Mở **Issue** mới, ghi rõ:
- Bước tái hiện lỗi (chạy lệnh nào, với file / kịch bản nào).
- Kết quả thực tế vs kết quả mong đợi.
- Môi trường: hệ điều hành, Python, ffmpeg (nếu liên quan).
- Log lỗi / ảnh chụp màn hình nếu có.

Không mở Issue để hỏi key, mật khẩu, hay xin token của người khác.

## Chuẩn bắt buộc cho mọi đóng góp vào repo này

Mọi PR đều phải giữ đúng chuẩn này, nếu không sẽ bị yêu cầu sửa lại:

- **Video:** dọc **9:16**, dài **30–45 giây** (trừ khi PR ghi rõ lý do ngoại lệ).
- **Giọng:** **1 giọng nữ duy nhất** xuyên suốt video. **Tốc độ `atempo 1.07x`** (giữ nguyên cao độ).
- **CẤM đổi cao độ** (`asetrate` / resample / bất kỳ cách nào làm giọng nheo nhéo như chipmunk).
- **Ngắt nghỉ:** **0,5s trước câu chốt / giải pháp**, **0,3s giữa các câu**, **0,8s đuôi**. Không cắt chữ, không tăng tốc toàn bộ để ép khung.
- **Phụ đề:** phụ đề cháy, **FontSize 11**, sát đáy (MarginV 14–16), không che mặt nhân vật, không đè lên phần hình đã vẽ kín đáy — chừa đáy trống cho phụ đề.
- **Không đẩy lên repo:** `.env`, `.venv/`, `*.mp4`, `*.m4a`, `*.mp3`, `*.wav`, `tts-cache/`. Video mẫu chỉ gửi link, không đẩy file video nặng lên repo.
- **Không dán key / token / mật khẩu** vào chat, code, Issue hay PR. Key Vbee để trong `.env` ở máy của bạn (file này đã nằm trong `.gitignore`).
- **Giữ `LICENSE` MIT** và dòng ghi nguồn `geeklee/srt-whiteboard-animation` trong README. Không xóa ghi nguồn.

## Test trước khi gửi PR

Trước khi gửi PR, bạn cần tự kiểm tra:

1. Chạy kiểm tra môi trường:
   ```bash
   python scripts/prepare_env.py --check
   ```
2. Chạy thử **1 video mẫu** từ đầu tới cuối bằng quy trình trong `HUONG-DAN-NGUOI-VIET.md`.
3. Kiểm tra video đầu ra:
   - Phụ đề khớp câu đang đọc, không che hình.
   - Tiếng rõ, không câm, không vỡ tiếng.
   - Giọng là 1 người duy nhất, không đoạn nào nheo nhéo / như người khác.
   - Video dọc 9:16, đúng chuẩn giọng và ngắt nghỉ ở trên.

Nếu PR chỉ sửa tài liệu, chỉ cần đọc lại file đã sửa để đảm bảo link, lệnh và tên file còn đúng.

## Quy tắc chung

- Viết tài liệu bằng tiếng Việt, ngắn gọn, ví dụ cụ thể.
- Một PR chỉ làm một việc. Đừng gộp nhiều tính năng / sửa lỗi không liên quan vào cùng một PR.
- Giữ thay đổi nhỏ, dễ xem lại. PR lớn, khó xem lại sẽ bị yêu cầu tách nhỏ.
