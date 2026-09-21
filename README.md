<h1 align="center">PantryChef AI 🍳</h1>

<p align="center">
  <i>Mạng xã hội chia sẻ công thức nấu ăn và Quản lý thực phẩm cá nhân tích hợp Trí tuệ Nhân tạo.</i>
</p>

<p align="center">
  <a href="https://flutter.dev"><img src="https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white" alt="Flutter"></a>
  <a href="https://supabase.com/"><img src="https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white" alt="Supabase"></a>
  <a href="https://dart.dev/"><img src="https://img.shields.io/badge/dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white" alt="Dart"></a>
  <a href="https://bloclibrary.dev/"><img src="https://img.shields.io/badge/BLoC-Feature%20Architecture-blue?style=for-the-badge" alt="BLoC Architecture"></a>
</p>

---

## 📖 Giới thiệu

Tình trạng lãng phí thực phẩm trong các hộ gia đình đang ngày càng gia tăng do việc không kiểm soát được hạn sử dụng và số lượng nguyên liệu sẵn có. Đồng thời, nhu cầu tìm kiếm, học hỏi và chia sẻ các công thức nấu ăn mới lạ luôn là niềm đam mê của rất nhiều người. 

**PantryChef AI** được xây dựng nhằm giải quyết bài toán trên thông qua một hệ sinh thái toàn diện, biến chiếc điện thoại của bạn thành một "Quản gia nhà bếp" thực thụ.

---

## ✨ Tính năng nổi bật (5 Khối Chức năng)

1. 👤 **Quản lý Tài khoản & Cá nhân hóa:** Xây dựng hồ sơ người dùng, theo dõi và kết nối cộng đồng.
2. 🧊 **Quản lý Tủ lạnh Thông minh:** Kiểm kê nguyên liệu, theo dõi hạn sử dụng, phân loại và cảnh báo hết hạn tự động.
3. 🍲 **Mạng xã hội Công thức:** Đăng tải, chia sẻ công thức, bình luận, yêu thích và lưu trữ bài đăng.
4. 🤖 **Trợ lý Trí tuệ Nhân tạo (AI Chef):** Tích hợp Gemini/OpenAI để gợi ý món ăn từ nguyên liệu sẵn có, đề xuất thay thế nguyên liệu và viết nội dung đăng bài tự động.
5. 📊 **Quản trị, Thống kê & Thông báo:** Hệ thống giám sát, phân tích tương tác và gửi Push Notification (thông báo hết hạn thực phẩm thời gian thực).

---

## 🛠 Công nghệ sử dụng

- **Frontend:** [Flutter](https://flutter.dev/) (Hỗ trợ iOS/Android)
- **Kiến trúc:** Feature-based Clean Architecture
- **State Management:** BLoC (Business Logic Component)
- **Backend & Database:** [Supabase](https://supabase.com/) (PostgreSQL, Auth, Storage)
- **Trí tuệ nhân tạo (AI):** Gemini API / OpenAI API

---

## 📂 Cấu trúc thư mục

Dự án sử dụng cấu trúc **Monorepo**:
- `/app`: Chứa toàn bộ mã nguồn ứng dụng Flutter. (Tất cả lệnh `flutter` sẽ chạy tại đây)
- `/docs`: Lưu trữ tài liệu phân tích kỹ thuật và mô tả dự án.
- `/process`: Tài liệu quản lý quy trình phát triển.

---

## 🚀 Hướng dẫn cài đặt (Getting Started)

### Yêu cầu hệ thống
- Flutter SDK (>= 3.0.0)
- Dart SDK
- Tài khoản Supabase (Để kết nối Database)

### Các bước chạy dự án

1. **Clone repository:**
   ```bash
   git clone https://github.com/your-username/pantry_chef_ai.git
   cd pantry_chef_ai
   ```

2. **Di chuyển vào thư mục ứng dụng Flutter:**
   ```bash
   cd app
   ```

3. **Cài đặt các thư viện phụ thuộc:**
   ```bash
   flutter pub get
   ```

4. **Chạy ứng dụng:**
   ```bash
   flutter run
   ```

---

## 👥 Đội ngũ Phát triển

Dự án được xây dựng bởi nhóm gồm 5 thành viên với sự phân công rõ ràng:

| Thành viên | Trách nhiệm chính |
| :--- | :--- |
| **Thành viên 1** | Khối 1: Quản lý Tài khoản, Supabase Auth, Hồ sơ Cá nhân |
| **Thành viên 2** | Khối 2: Quản lý Tủ lạnh, CRUD nguyên liệu, Tracking hạn sử dụng |
| **Thành viên 3** | Khối 3: Mạng xã hội, UI/UX Feed, Tương tác (Like, Comment, Bookmark) |
| **Thành viên 4** | Khối 4: Tích hợp AI (Gemini/OpenAI), Xử lý Prompt gợi ý món ăn & nội dung |
| **Thành viên 5** | Khối 5: Quản trị (Admin Panel), Thống kê dữ liệu, Push Notifications |

> **Xem chi tiết tài liệu thiết kế hệ thống tại:** [`docs/project_overview.md`](./docs/project_overview.md)
