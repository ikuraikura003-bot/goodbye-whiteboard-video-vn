# Hướng dẫn người Việt — Làm video đầu tiên

Bản này hướng tới người Việt: mặc định video **dọc 9:16, 30–45 giây** cho Reels / TikTok, giọng Việt, caption Facebook + TikTok kèm theo.

## 3 bước chạy video đầu tiên

### Bước 1 — Cài đặt

Cần có **Python 3.10+** và **ffmpeg** trong PATH.

```bash
git clone https://github.com/ikuraikura003-bot/goodbye-whiteboard-video-vn.git
cd goodbye-whiteboard-video-vn
python scripts/prepare_env.py
```

### Bước 2 — Làm video từ 1 chủ đề

Mở thư mục này bằng AI agent (Claude Code / Codex / Antigravity) và nói:

```text
Dùng skill whiteboard-video làm video vẽ tay 40 giây về chủ đề "Vì sao ngủ đủ 8 tiếng mà vẫn mệt?".
Giọng nữ, dọc 9:16, có phụ đề. Trả lời bằng tiếng Việt.
```

Agent sẽ dừng sau mỗi bước để bạn duyệt: kịch bản → giọng đọc → ảnh → chia vùng → render → video cuối. Trả lời "ok / chốt" để đi tiếp.

### Bước 3 — Đăng Reels / TikTok

Mỗi video cuối nên kèm 2 caption:

- **Facebook:** tiêu đề + tóm tắt 1 ý + câu hỏi kéo bình luận + 5–8 hashtag tiếng Việt.
- **TikTok:** ngắn, hook mạnh + câu hỏi + hashtag trend + hashtag kênh.

Đăng cách nhau ít nhất 6 tiếng nếu đăng 2 video/ngày (ví dụ: 11h–12h + 19h–21h). Không mua follow / view.

## Cách chọn giọng

| Nhu cầu | Chọn gì |
|---|---|
| Miễn phí, dùng ngay | Edge TTS: `vi-VN-HoaiMyNeural` (nữ) hoặc `vi-VN-NamMinhNeural` (nam) |
| Nghe tự nhiên hơn, trả phí theo ký tự | Vbee — dán mã giọng copy từ giao diện Vbee vào `.env` |
| Kể chuyện cảm xúc | Giọng nữ, tốc độ 1.0–1.07x |
| Giải thích kiến thức / tài chính | Giọng nam hoặc nữ đều được, giữ nhịp đều |

Cấu hình trong `.env` (copy từ `.env.example`, **không commit `.env`**):

```env
TTS_PROVIDER=edge
TTS_VOICE=vi-VN-HoaiMyNeural
TTS_SPEED=1.07
```

## Chuẩn giọng của bản này (bắt buộc)

Để tránh lỗi giọng nheo nhéo / chipmunk từng gặp:

- **1 giọng duy nhất** xuyên suốt video, không đổi giọng giữa các câu.
- **Chỉ dùng `atempo` 1.07x** để tăng tốc (giữ nguyên cao độ). **Cấm `asetrate` / đổi cao độ.**
- Ngắt nghỉ: **0,5s trước câu chốt**, **0,3s giữa các câu**, **0,8s đuôi**.
- Tách câu ngắn (≤ 9–12 từ), dùng dấu `!` / `?` để lên giọng tự nhiên.
- Không tăng tốc toàn bộ để ép khung — nếu giọng dài thì kéo dài hình vẽ cho khớp.

## Mẹo để video đẹp

- Mỗi video **1 ý duy nhất**, hook trong 2 giây đầu, kết bằng 1 câu hỏi.
- Mỗi cảnh 1 ý chính, 20–35 giây. Câu phụ đề ≤ 5 giây đọc.
- Ảnh cảnh: nền kem `#F5EBD7`, không chữ / số / logo trong ảnh.
- Luôn xem ảnh kiểm tra vùng trước khi render — sửa ở đó nhanh hơn render lại.
- Khung đầu không để trắng trống: nên có sẵn hình + câu hook để giữ người xem.

## Lỗi thường gặp

| Lỗi | Cách sửa |
|---|---|
| Phụ đề che mặt nhân vật | Đẩy phụ đề sát đáy (MarginV 14–16), chừa đáy trống cho phụ đề |
| Giọng bị nheo / như người khác | Đã dùng đổi cao độ — làm lại, chỉ dùng `atempo`, không dùng `asetrate` |
| Giọng chậm | Tăng `atempo` tối đa 1.08x, rút ngắt nghỉ, không vượt quá |
| Key Vbee lỗi | Kiểm tra `.env`, không dán key vào khung chat |

## Giấy phép

MIT — xem `LICENSE`. Dựa trên ý tưởng từ `geeklee/srt-whiteboard-animation` (MIT).
