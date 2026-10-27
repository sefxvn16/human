# human

[English](README.md) | **Tiếng Việt**

Skill cho trợ lý AI giúp gỡ các khuôn mẫu đặc trưng của văn AI khỏi văn bản hoàn thiện: từ sáo rỗng thay cho dữ kiện, liệt kê bộ ba máy móc, cân bằng giả, phân tích gắn đuôi, câu chốt kiểu khẩu hiệu. Dùng được cho cả tiếng Việt và tiếng Anh. Hướng dẫn trong `SKILL.md` viết bằng tiếng Việt.

## Skill làm gì

Mô hình ngôn ngữ có xu hướng thay chi tiết cụ thể, hiếm bằng cách nói chung, tích cực, hợp với mọi trường hợp. Văn bản vì thế vừa mờ vừa phóng đại. Skill xử lý nguyên nhân chứ không chỉ bề mặt: giữ chi tiết thật có trong đầu vào thay vì đổi từ này sang từ khác.

- **4 nguyên tắc nền** đứng trên mọi quy tắc: không bịa, theo chuẩn của thể loại, quy tắc là phép kiểm chứ không phải chỉ tiêu, giữ nghĩa của người viết.
- **20 điều cần tránh**, như từ rỗng, negative parallelism, false range, nguồn mơ hồ, câu tóm tắt lặp, cấu trúc công thức, giấu chủ thể hành động, cân bằng giả, đổi đồng nghĩa cho thuật ngữ.
- **Trước khi viết:** kiểm dữ kiện chưa xác nhận và người đọc mục tiêu, hỏi gộp một lượt.
- **Tự kiểm trước khi giao:** rà theo 20 điều, phép thử cụ thể, phép thử khuôn mới, rồi chấm 5 tiêu chí (thẳng, nhịp, tin người đọc, tự nhiên, cô đọng). Dưới 35/50 thì sửa tiếp.
- **Giọng riêng của bạn:** dán 2–3 đoạn văn của chính bạn, skill sẽ bám theo nhịp câu, từ vựng và dấu câu của mẫu (ví dụ giữ em dash nếu mẫu có dùng). Mẫu thắng các quy tắc về hình thức, không thắng nguyên tắc nền và các quy tắc về nội dung.
- **Rà soát văn bản có sẵn:** liệt kê vi phạm theo số điều, báo điểm, rồi đưa bản đã sửa, không đổi mức khẳng định, thuật ngữ và số liệu.

## Ranh giới

- Áp dụng cho văn bản hoàn thiện người dùng sẽ gửi đi hoặc xuất bản: hồ sơ ứng tuyển, thư, báo cáo, bài luận, nội dung website và mạng xã hội, văn bản hành chính hoặc pháp lý.
- **Không** áp dụng cho câu trả lời trao đổi, giải thích, phân tích thông thường trong chat.
- Chỉ xử lý hình thức diễn đạt. Skill không làm nội dung sâu hơn hay có căn cứ hơn.
- Skill không phải công cụ qua mặt phần mềm phát hiện AI và không bảo đảm kết quả với chúng.

## Cấu trúc thư mục

```
human/
  SKILL.md
  references/
    vietnamese-patterns.md   # Ví dụ nhận diện bằng tiếng Việt
    english-patterns.md      # Danh sách cụm từ và cấu trúc tiếng Anh
    LICENSE-stop-slop.txt    # Giấy phép MIT của phần chuyển thể
README.md
README.vi.md
LICENSE.md
```

## Cài đặt

### Ứng dụng Claude (claude.ai, Claude desktop)

1. Tải repo về, nén riêng thư mục `human` thành `human.zip` (file zip phải chứa thư mục `human` ở cấp ngoài cùng).
2. Mở Claude, vào **Customize → Skills**, bấm **+** → **Create skill** → **Upload a skill** và chọn `human.zip`. Tên và vị trí menu có thể khác tùy phiên bản ứng dụng. Skill cần bật tính năng chạy mã (code execution).
3. Kiểm tra skill `human` đã hiện trong danh sách và đang bật.

### Claude Code

Chép thư mục `human` vào `~/.claude/skills/` (dùng cho mọi dự án) hoặc `.claude/skills/` của một dự án, rồi khởi động lại Claude Code.

## Cách dùng

Skill kích hoạt khi bạn nhờ soạn một văn bản hoàn thiện, hoặc đưa một văn bản và nhờ sửa cho bớt giọng AI. Cũng có thể gọi trực tiếp bằng `/human`. Ví dụ:

- "Viết thư xin việc cho vị trí này: …"
- "/human Rà bản báo cáo này, sửa những chỗ nghe như văn AI, giữ nguyên số liệu."

## Giới hạn

- Danh sách mẫu tiếng Việt dựa trên quan sát và các nguồn tiếng Anh, chưa có nghiên cứu tiếng Việt nào được kiểm chứng làm căn cứ.
- Điểm chấm là công cụ nội bộ để tự kiểm, không phải phép đo.
- Không có bộ dấu hiệu nào đủ tin cậy để kết luận một văn bản do AI viết.

## Góp ý

Mọi góp ý xin gửi qua mục **Issues** của repo. Nên ghi: văn bản gốc và yêu cầu của bạn (đã bỏ thông tin cá nhân hoặc thông tin mật), kết quả bạn mong đợi và kết quả thực tế.

## Giấy phép

Skill phát hành theo giấy phép **CC BY-NC 4.0**: dùng miễn phí cho mục đích phi thương mại, cần ghi nguồn. Muốn dùng thương mại, vui lòng liên hệ tác giả qua mục **Issues**. Phần của bên thứ ba nêu trong [LICENSE.md](LICENSE.md).
