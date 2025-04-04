# AttendanceBot - Hệ Thống Điểm Danh Tự Động Trên Telegram

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## Giới Thiệu
`AttendanceBot` là một hệ thống tự động hóa việc điểm danh nhân viên thông qua Telegram. Dự án sử dụng các công nghệ như xử lý hình ảnh (MediaPipe, OpenCV), tích hợp Google Sheets, và bot Telegram để:
- Theo dõi tin nhắn điểm danh trong nhóm Telegram.
- Phát hiện cử chỉ tay từ ảnh để kiểm tra tính hợp lệ.
- Tạo báo cáo điểm danh chi tiết, bao gồm danh sách nhân viên chưa điểm danh và vi phạm.

Dự án được thiết kế để hỗ trợ quản lý nhân sự trong các tổ chức, đặc biệt là các nhóm làm việc từ xa.

## Tính Năng
- **Quản lý ca làm việc**: Tự động xác định ca hiện tại dựa trên thời gian.
- **Xử lý hình ảnh**: Phát hiện cử chỉ tay để tránh trùng lặp.
- **Tích hợp Google Sheets**: Lấy danh sách nhân viên và lịch nghỉ.
- **Báo cáo tự động**: Gửi báo cáo qua bot Telegram với định dạng Markdown đẹp mắt.
- **Kiểm tra vi phạm**: Phát hiện nhân viên sử dụng cùng cử chỉ tay trong các ca.

## Yêu Cầu
- Python 3.8 trở lên
- Tài khoản Telegram và API credentials (API_ID, API_HASH, BOT_TOKEN)
- Tài khoản Google Cloud với Service Account để truy cập Google Sheets
- API key từ TimeZoneDB (tùy chọn)

## Cài Đặt
1. **Clone repository**:
   ```bash
   git clone https://github.com/[username]/AttendanceBot.git
   cd AttendanceBot

2. **Cài đặt các thư viện**:
   ```bash
   pip install -r requirements.txt
   
3. **Cấu hình biến môi trường**:
- Sao chép tệp .env.example (nếu có) thành .env trong thư mục GG_console/:
   ```bash
   cp GG_console/.env.example GG_console/.env

- Sao chép tệp .env.example (nếu có) thành .env trong thư mục GG_console/:
   ```text
   API_ID_PRINO=your_api_id
   API_HASH_PRINO=your_api_hash
   PHONE_NUMBER_PRINO=your_phone_number
   TELEGRAM_BOT_TOKEN_Checkvar=your_bot_token
   SPREADSHEETS_OFF_BPTK=your_spreadsheet_id
   GID_OFF_BPTK=your_gid_off
   GID_STAFF_BPTK=your_gid_staff
   TIMEZONE_API_KEY=your_timezone_api_key
   ALLOWED_CHAT_IDS_ID_DIEM_DANH=your_chat_id

4. **Cấu hình biến môi trường**:
Đặt tệp JSON của Google Service Account vào đường dẫn: K:/GG_console/check-lich-off/information-user_OKVIP.json (hoặc thay đổi đường dẫn trong mã nguồn).

## Cách Sử Dụng
1. **Chạy chương trình**:
   ```bash
   python attendance_bot.py
- Lần đầu chạy, bạn sẽ cần nhập mã xác nhận Telegram và mật khẩu 2FA (nếu có).

2. **Gửi lệnh điểm danh**:
- Trong nhóm Telegram được cấu hình (SOURCE_CHAT_ID), gửi lệnh /checkvar để bắt đầu quá trình kiểm tra.
- Bot sẽ tự động quét tin nhắn, xử lý ảnh, và gửi báo cáo sau 5 phút.

3. **Gửi lệnh điểm danh**:
- Báo cáo sẽ được gửi đến DESTINATION_CHAT_ID với danh sách nhân viên chưa điểm danh và vi phạm (nếu có).
Cấu Trúc Dự Án

## Cấu Trúc Dự Án
   ```text
   AttendanceBot/
   ├── GG_console/
   │   └── .env              # Biến môi trường (không commit)
   ├── output/               # Thư mục lưu ảnh và tệp đầu ra
   ├── info-message.txt      # Tệp lưu tin nhắn đã quét
   ├── attendance_bot.py     # Mã nguồn chính
   ├── requirements.txt      # Danh sách thư viện
   ├── README.md             # Tài liệu này
   └── .gitignore            # Tệp bỏ qua
   ```

## Góp Ý và Đóng Góp
- Nếu bạn tìm thấy lỗi hoặc muốn cải thiện dự án, hãy mở một Issue hoặc gửi Pull Request.
- Liên hệ telegram: [CA PRINO - TT DESIGN - TỔ 1](https://t.me/prino_pNetwork)

## Giấy Phép
Chưa được cấp phép...

## Lưu Ý
- Đảm bảo cấu hình đúng các thông tin nhạy cảm trong .env.
- Kiểm tra kết nối mạng và quyền truy cập Google Sheets trước khi chạy.




