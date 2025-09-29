# NewsFlow-AI
NewsFlow AI là hệ thống tự động hóa tin tức được xây dựng trên nền tảng n8n kết hợp AI (Google Gemini), nhằm thu thập – đánh giá – biên tập – xuất bản tin tức lên mạng xã hội. Mục tiêu là giúp đội ngũ truyền thông rút ngắn thời gian xử lý tin, ưu tiên tin hot và chuẩn hóa nội dung theo phong cách nhất quán.

# Features

- Thu thập dữ liệu từ RSS feed của các trang báo lớn ( Ở đây mình lấy từ https://vnexpress.net ).
- Loại bỏ trùng lặp để giữ lại tin mới nhất.
- Đánh giá “độ hot” của tin bằng AI (scoring 1–10).
- Viết lại nội dung súc tích, dễ đọc, chuẩn mạng xã hội.
- Tự động sinh hashtag dựa trên nội dung tin.
- Tin tức đã biên tập được duyệt qua Telegram – người quản trị có thể phê duyệt hoặc từ chối trước khi xuất bản.
- Cập nhật hình ảnh & nội dung tự động lên template (Google Slides) để làm visuals.
- Xuất bản tin tức: đăng bài + ảnh + hashtag lên Facebook.
- Lưu trữ & theo dõi trạng thái (Chưa duyệt / Đã đăng / Không duyệt) trong Google Sheets.

# Architecture/ Kiến trúc hệ thống

- n8n workflows: Điều phối toàn bộ pipeline tin tức.
- Google Gemini (AI): Đánh giá viral score, viết lại bài, sinh hashtag.
- Telegram Bot: Giao diện phê duyệt bản nháp.
- Facebook Graph API:	Xuất bản bài viết + ảnh.
- Google Sheets:	Lưu metadata & trạng thái tin.
- Google Slides:	Sinh template hình ảnh minh họa.

Pipeline tổng quan:
Nguồn tin → Lọc & xử lý → AI đánh giá + viết lại → Gửi duyệt (Telegram) → Xuất bản (Facebook) → Lưu log (Google Sheets) + Visual (Google Slides).

<img width="1150" height="683" alt="image" src="https://github.com/user-attachments/assets/00479cf1-dc19-4d87-ab8d-46bea0fbe8f7" />

Luồng 1: Nguồn tin → Lọc 10 tin tức & xử lý → AI đánh giá 10 bài báo
<img width="1677" height="442" alt="image" src="https://github.com/user-attachments/assets/88086d7c-b5d3-4952-9db5-b19b524699de" />

Luồng 2: Viết lại nội dung → Gửi duyệt (Telegram) → Xuất bản (Facebook) → Lưu log (Google Sheets).
<img width="1504" height="628" alt="image" src="https://github.com/user-attachments/assets/e1bf1ef4-bf4c-410f-9b64-603e191ecc2b" />

# Highlights

- End-to-end automation: từ thu thập đến xuất bản.
- AI-driven workflow: tự động đánh giá & viết lại tin tức.
- Multi-channel integration: Telegram, Facebook, Google API.
- Business value rõ ràng: giảm 70–80% thời gian biên tập, tăng tốc độ phản ứng với tin hot.

# Giá trị đạt được
- Tiết kiệm thời gian: từ nhiều giờ biên tập xuống vài phút.
- Tăng hiệu quả: tập trung vào tin hot, bỏ qua tin ít giá trị.
- Chuẩn hóa nội dung: giọng văn nhất quán, dễ đọc.
- Khả năng mở rộng: dễ dàng thêm nguồn tin hoặc kênh xuất bản mới.
