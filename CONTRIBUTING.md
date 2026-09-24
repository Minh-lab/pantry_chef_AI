# Hướng dẫn đóng góp (Contributing Guidelines)

Tài liệu này quy định quy trình quản lý chất lượng code, cách tạo nhánh và quy ước commit cho dự án.

## 1. Branching Strategy (Chiến lược tạo nhánh)
Dự án sử dụng mô hình nhánh đơn giản nhưng hiệu quả:
- `main` (hoặc `master`): Chứa code ổn định, sẵn sàng release lên store.
- `develop`: Nhánh tích hợp chính. Các tính năng mới sẽ được gộp vào đây trước.
- **Nhánh làm việc**: Luôn tạo từ nhánh `develop`. Đặt tên theo chuẩn:
  - `feat/<tên-tính-năng>` (VD: `feat/login-screen`)
  - `fix/<tên-lỗi>` (VD: `fix/crash-on-startup`)
  - `refactor/<tên-chức-năng>` (VD: `refactor/api-client`)
  - `docs/<tên-tài-liệu>`

## 2. Commit Convention (Quy ước Commit)
Sử dụng [Conventional Commits](https://www.conventionalcommits.org/).
**Cú pháp:** `<type>: <description>`

- `feat`: Tính năng mới (tạo UI, thêm logic).
- `fix`: Sửa một lỗi (bug).
- `docs`: Cập nhật tài liệu (README, comments...).
- `style`: Format code, không đổi logic (linting, format...).
- `refactor`: Viết lại code nhưng không thay đổi tính năng.
- `test`: Thêm/sửa test case.
- `chore`: Cập nhật cấu hình build, dependencies (`pubspec.yaml`, `CI/CD`).

*Ví dụ:* `feat: add Google login button` hoặc `fix: resolve crash on null user`

## 3. Quy trình Pull Request (PR)
Để đưa code từ nhánh làm việc của bạn vào `develop`, hãy tuân thủ quy trình sau:

1. **Cập nhật code mới nhất:** 
   `git checkout develop`
   `git pull origin develop`
   `git checkout <nhánh-của-bạn>`
   `git merge develop` (hoặc rebase) và giải quyết conflicts nếu có.
2. **Kiểm tra local:**
   Chạy `fvm flutter format .` và `fvm flutter analyze` để đảm bảo code sạch.
3. **Push nhánh và tạo PR:**
   Push code lên Github, tạo Pull Request hướng vào nhánh `develop`.
4. **Điền PR Template:**
   Điền đầy đủ thông tin vào form (mô tả, checklist) được Github tự động tải lên.
5. **CI & Code Review:**
   - GitHub Actions (CI) phải chạy **Pass xanh** (format, lint, build).
   - Tag ít nhất 1 thành viên trong team để Review. Nhận ít nhất **1 Approve**.
   - Sửa code dựa trên comment của reviewer (nếu có).
6. **Merge:**
   Khi đã thỏa mãn mọi điều kiện, sử dụng tính năng **Squash and Merge** để gộp PR (giữ lịch sử git gọn gàng trên `develop`).
