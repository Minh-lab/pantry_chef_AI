# Pantry Chef AI 🍳

Dự án ứng dụng di động (Flutter) thông minh giúp quản lý thực phẩm trong tủ lạnh và gợi ý công thức nấu ăn dựa trên nguyên liệu sẵn có, tích hợp AI.

## 👥 Đội ngũ phát triển (Team Members)

| STT | MSSV | Họ và Tên | Vai trò |
| :---: | :---: | :--- | :--- |
| 1 | 2351170607 | Nguyễn Minh | Nhóm trưởng |
| 2 | 2251061770 | MÔNG THỊ BÍCH HẠNH | Thành viên |
| 3 | 2251161967 | NGUYỄN TIẾN ĐẠT | Thành viên |
| 4 | 2351170579 | Dương Hải Đăng | Thành viên |
| 5 | 2351170612 | Nguyễn Hữu Quân | Thành viên |

## 🚀 Yêu cầu hệ thống
- [FVM (Flutter Version Management)](https://fvm.app/)
- Flutter SDK (được quản lý tự động qua FVM)
- Trình giả lập (iOS Simulator / Android Emulator) hoặc thiết bị thật.

## 🛠 Hướng dẫn cài đặt & Chạy dự án

**Bước 1: Clone dự án**
```bash
git clone https://github.com/Minh-lab/pantry_chef_AI.git
cd pantry_chef_AI
```

**Bước 2: Cài đặt Flutter SDK (qua FVM)**
Đảm bảo bạn đã cài FVM trên máy, sau đó chạy lệnh sau tại thư mục gốc:
```bash
fvm install
fvm use
```

**Bước 3: Thiết lập biến môi trường**
Dự án sử dụng các biến môi trường để bảo mật API Key. Hãy copy file template và điền thông tin thật:
```bash
cp .env.example .env
```
*(Mở file `.env` và nhập các API keys cần thiết. File `.env` đã được gitignore để không bị đẩy lên mạng)*

**Bước 4: Cài đặt dependencies**
```bash
fvm flutter pub get
```

**Bước 5: Chạy ứng dụng**
```bash
fvm flutter run
```

## 🤝 Tham gia phát triển
Vui lòng đọc kỹ file [CONTRIBUTING.md](CONTRIBUTING.md) để nắm bắt **Quy trình Pull Request**, **Branching Strategy**, và **Commit Convention** của nhóm trước khi bắt đầu viết code.
