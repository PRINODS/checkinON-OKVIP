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
