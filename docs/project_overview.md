# Báo cáo Tổng hợp Đề tài Dự án

## 1. Giới thiệu đề tài

* **Tên đề tài:** PantryChef AI - Mạng xã hội chia sẻ công thức nấu ăn và quản lý thực phẩm cá nhân tích hợp Trí tuệ Nhân tạo.
* **Bối cảnh & Mục tiêu:**
  Tình trạng lãng phí thực phẩm trong các hộ gia đình đang ngày càng gia tăng do việc không kiểm soát được hạn sử dụng và số lượng nguyên liệu sẵn có. Đồng thời, nhu cầu tìm kiếm, học hỏi và chia sẻ các công thức nấu ăn mới lạ luôn là niềm đam mê của rất nhiều người. 
  Dự án PantryChef AI được xây dựng nhằm giải quyết bài toán trên thông qua một hệ sinh thái toàn diện bao gồm 5 khối chức năng kết hợp chặt chẽ:
  * **Khối Quản lý Tài khoản & Cá nhân hóa:** Xây dựng hồ sơ người dùng, theo dõi và kết nối cộng đồng.
  * **Khối Quản lý Tủ lạnh Thông minh:** Kiểm kê nguyên liệu, theo dõi hạn sử dụng và cảnh báo hết hạn tự động.
  * **Khối Mạng xã hội Công thức:** Đăng tải, chia sẻ công thức, bình luận, yêu thích và lưu trữ bài đăng.
  * **Khối Trợ lý Trí tuệ Nhân tạo (AI Chef):** Dựa trên nguyên liệu còn lại trong tủ lạnh để gợi ý món ăn, biến tấu công thức hoặc tạo mô tả bài đăng tự động.
  * **Khối Quản trị, Thống kê & Thông báo:** Hệ thống admin giám sát nội dung, gửi thông báo đẩy (Push Notification) thời gian thực và báo cáo dữ liệu người dùng.

* **Công nghệ sử dụng:**
  * **Frontend:** Flutter (Mobile App) — Hỗ trợ xây dựng giao diện đa nền tảng (iOS/Android) mượt mà và linh hoạt.
  * **State Management:** BLoC (Business Logic Component) — Tách biệt UI và Logic, dễ dàng mở rộng và bảo trì.
  * **Backend, Cơ sở dữ liệu & Storage:** **Supabase (PostgreSQL)** — Quản lý xác thực (Auth), lưu trữ dữ liệu quan hệ, và lưu trữ hình ảnh/video món ăn (Supabase Storage).
  * **AI Integration:** Trình xử lý API tích hợp **Gemini API / OpenAI API** để phân tích nguyên liệu và sáng tạo nội dung chữ (LLM).
  * **Kiến trúc:** Feature-based Clean Architecture — Phân tách mã nguồn theo từng tính năng độc lập (auth, pantry, recipe...).

---

## 2. Bảng phân công & Danh mục Chức năng Tổng quan

| **Tên khối chức năng**                                                                     | **Thành viên thực hiện** | **Tác nhân chính**        | **Danh mục các Use Case chi tiết**                                                                                                                                                             |
| :----------------------------------------------------------------------------------------- | :----------------------- | :------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Khối 1: Quản lý Tài khoản & Hồ sơ Cá nhân** *(Account & Profile Management)*             | **Thành viên 1**         | Người dùng                | **UC 1.1:** Đăng ký / Đăng nhập (Email, Google)<br>**UC 1.2:** Quản lý thông tin hồ sơ (Avatar, Tiểu sử)<br>**UC 1.3:** Theo dõi (Follow) người dùng khác                                      |
| **Khối 2: Quản lý Thực phẩm & Tủ lạnh Thông minh** *(Smart Pantry & Inventory)*            | **Thành viên 2**         | Người dùng                | **UC 2.1:** Thêm/Xóa/Sửa danh mục nguyên liệu<br>**UC 2.2:** Cài đặt hạn sử dụng cho thực phẩm<br>**UC 2.3:** Hệ thống nhắc nhở thực phẩm sắp hết hạn                                          |
| **Khối 3: Mạng xã hội Chia sẻ Công thức** *(Recipe Social Network)*                        | **Thành viên 3**         | Người dùng                | **UC 3.1:** Đăng tải công thức (Hình ảnh, Các bước làm)<br>**UC 3.2:** Tương tác bài viết (Thích, Bình luận, Chia sẻ)<br>**UC 3.3:** Lưu trữ công thức vào Bộ sưu tập cá nhân                  |
| **Khối 4: Trợ lý Nấu ăn AI** *(AI Chef Assistant)*                                         | **Thành viên 4**         | Người dùng, Hệ thống AI   | **UC 4.1:** Gợi ý món ăn từ nguyên liệu tủ lạnh<br>**UC 4.2:** Gợi ý nguyên liệu thay thế khi nấu ăn<br>**UC 4.3:** AI hỗ trợ viết caption bài đăng chuẩn SEO                                  |
| **Khối 5: Quản trị Hệ thống, Thống kê & Thông báo** *(Admin, Analytics & Notification)*    | **Thành viên 5**         | Admin, Hệ thống ngầm      | **UC 5.1:** Quản lý và kiểm duyệt nội dung người dùng<br>**UC 5.2:** Thống kê tương tác và số lượng nguyên liệu<br>**UC 5.3:** Gửi Push Notification (Tin tức mới, Tương tác)                  |

---

## 3. Kiến trúc Luồng Thực hiện Dự án

Sơ đồ luồng phát triển và tích hợp theo từng giai đoạn dựa trên sự phụ thuộc dữ liệu giữa **5 Khối Chức năng Cốt lõi**:

```text
[GIAI ĐOẠN 0: KẾT NỐI NỀN TẢNG DÙNG CHUNG]
- Khởi tạo Repository & Cấu trúc Clean Architecture (Flutter)
- Khởi tạo Supabase Project (Auth, PostgreSQL Database, Storage)
- Thiết lập Schema Dữ liệu cốt lõi (users, ingredients, recipes, posts, notifications)
                                │
        ┌───────────────────────┼───────────────────────┐
        │                       │                       │
[GIAI ĐOẠN 1: PHÁT TRIỂN SONG SONG BẬC 1 (CORE APP)]
● Khối 1: Tài khoản & Hồ sơ           ● Khối 2: Tủ lạnh Thông minh      ● Khối 3: Chia sẻ Công thức
  - Luồng Supabase Auth                 - CRUD Nguyên liệu                - Đăng tải hình ảnh lên Storage
  - Giao diện Profile cá nhân           - Xử lý ngày tháng hạn dùng       - Bảng Feed hiển thị bài viết
  - Mối quan hệ Follow/Unfollow         - Giao diện quản lý danh sách     - Nút Like, Comment realtime
        │                       │                       │
        └───────────────────────┼───────────────────────┘
                                │
                 [GIAI ĐOẠN 2: TÍCH HỢP TRÍ TUỆ NHÂN TẠO (AI) & TỰ ĐỘNG HÓA]
                 ● Khối 4: Trợ lý AI (AI Chef)
                   - Gửi danh sách nguyên liệu từ Khối 2 sang Gemini/OpenAI
                   - Xử lý Prompt để AI trả về công thức nấu ăn
                   - Hỗ trợ AI sinh nội dung bài đăng cho Khối 3
                 ● Khối 5: Báo cáo & Thông báo
                   - Tạo luồng Job chạy ngầm (Supabase Edge Functions) kiểm tra hạn sử dụng
                   - Gửi Push Notification cho người dùng khi có Tương tác mới hoặc Nguyên liệu hỏng
                                │
                 [GIAI ĐOẠN 3: KIỂM THỬ E2E, TỐI ƯU & ĐÓNG GÓI]
                 - Kiểm thử Toàn trình (End-to-End Testing) luồng: Nhập nguyên liệu -> AI Gợi ý -> Nấu ăn -> Đăng bài
                 - Tối ưu UI/UX, Xử lý lỗi Cache hình ảnh, Tối ưu truy vấn CSDL
                 - Đóng gói ứng dụng (APK/AAB cho Android, IPA cho iOS)
```

---

## 4. Phân tích Chi tiết Từng Khối Chức năng & Kịch bản Sử dụng (Use Case)

### Khối 1: Quản lý Tài khoản & Hồ sơ Cá nhân (Thành viên 1)

* **Giải pháp nghiệp vụ:** Xây dựng định danh an toàn cho mỗi đầu bếp gia đình. Mạng lưới Follow giúp kết nối những người có cùng sở thích ẩm thực.

#### Danh mục các Use Case:
1. **UC 1.1: Đăng ký / Đăng nhập:** Tích hợp Supabase Auth hỗ trợ đăng ký qua Email/Password và Social Login (Google). Mã hóa bảo mật và duy trì phiên đăng nhập (Session).
2. **UC 1.2: Quản lý thông tin hồ sơ:** Khách hàng có thể thay đổi Avatar, cập nhật tiểu sử, liên kết mạng xã hội, xem lại toàn bộ các bài đăng công thức của chính mình.
3. **UC 1.3: Theo dõi (Follow) người dùng:** Tạo kết nối cộng đồng, cho phép người dùng ấn "Theo dõi" các đầu bếp khác để ưu tiên hiển thị bài viết của họ trên bảng tin (Feed).

---

### Khối 2: Quản lý Thực phẩm & Tủ lạnh Thông minh (Thành viên 2)

* **Giải pháp nghiệp vụ:** Biến chiếc điện thoại thành "Quản gia" của nhà bếp. Giúp người dùng nắm chính xác mình đang có gì trong tủ lạnh, từ đó tiết kiệm chi phí mua sắm dư thừa.

#### Danh mục các Use Case:
1. **UC 2.1: Thêm/Xóa/Sửa danh mục nguyên liệu:** Cung cấp giao diện để người dùng thêm nhanh nguyên liệu (thịt, rau, gia vị...) kèm theo số lượng/trọng lượng.
2. **UC 2.2: Cài đặt hạn sử dụng:** Chọn ngày hết hạn cho từng loại thực phẩm, hệ thống sẽ gán nhãn màu sắc cảnh báo (Xanh: An toàn, Vàng: Sắp hết hạn, Đỏ: Đã quá hạn).
3. **UC 2.3: Bộ đếm và Phân loại:** Lọc thực phẩm theo danh mục (Thịt cá, Rau củ, Đồ khô), tự động sắp xếp ưu tiên hiển thị các thực phẩm gần hết hạn lên đầu.

---

### Khối 3: Mạng xã hội Chia sẻ Công thức (Thành viên 3)

* **Giải pháp nghiệp vụ:** Tạo sân chơi để người dùng khoe thành quả nấu nướng. Kích thích sự sáng tạo thông qua các tương tác tích cực từ cộng đồng.

#### Danh mục các Use Case:
1. **UC 3.1: Đăng tải công thức:** Giao diện cho phép upload hình ảnh thành phẩm, nhập tiêu đề, mô tả, danh sách nguyên liệu và các bước thực hiện chi tiết. Dữ liệu ảnh được lưu tại Supabase Storage.
2. **UC 3.2: Tương tác bài viết:** Hệ thống News Feed hiển thị các công thức mới nhất. Hỗ trợ tính năng Thả tim (Like), Bình luận (Comment) và đếm lượt xem (Views).
3. **UC 3.3: Lưu trữ công thức:** Tính năng "Đánh dấu" (Bookmark) giúp người dùng lưu các công thức hay của người khác vào bộ sưu tập cá nhân để dễ dàng mở lại khi vào bếp.

---

### Khối 4: Trợ lý Nấu ăn AI (AI Chef) (Thành viên 4)

* **Giải pháp nghiệp vụ:** Sử dụng LLM (Large Language Model) làm bộ não sáng tạo ẩm thực. Trợ lý ảo giúp phá vỡ sự nhàm chán của các món ăn thường ngày.

#### Danh mục các Use Case:
1. **UC 4.1: Gợi ý món ăn từ tủ lạnh:** Người dùng bấm nút "Hôm nay ăn gì?", ứng dụng thu thập danh sách thực phẩm đang có trong Khối 2, kết nối Gemini API để trả về danh sách 3-5 món ăn khả thi kèm theo công thức nấu.
2. **UC 4.2: Gợi ý thay thế nguyên liệu:** Khi một công thức yêu cầu "Rượu vang" nhưng người dùng không có, AI sẽ tự động phân tích và đề xuất thay bằng "Giấm táo + Đường" để giữ nguyên hương vị.
3. **UC 4.3: Hỗ trợ viết caption:** Tích hợp nút "AI Caption" tại màn hình đăng bài của Khối 3, giúp sinh ra những đoạn văn mô tả món ăn hấp dẫn, phù hợp để chia sẻ lên mạng xã hội.

---

### Khối 5: Quản trị Hệ thống, Thống kê & Thông báo (Thành viên 5)

* **Giải pháp nghiệp vụ:** Đảm bảo hệ thống hoạt động ổn định, môi trường cộng đồng văn minh và tăng cường tương tác (Retention) thông qua hệ thống thông báo đẩy.

#### Danh mục các Use Case:
1. **UC 5.1: Quản lý & Cảnh báo nội dung (Admin Panel):** Xây dựng trang Dashboard nội bộ, cho phép Admin ẩn các bài đăng vi phạm tiêu chuẩn cộng đồng, khóa tài khoản spam.
2. **UC 5.2: Thống kê hiệu suất:** Tính toán và vẽ biểu đồ về: Tổng số công thức được đăng, loại nguyên liệu nào được sử dụng nhiều nhất, số lượng thực phẩm được cứu khỏi việc lãng phí.
3. **UC 5.3: Gửi Thông báo (Push Notification):** Kết hợp Supabase Edge Functions / FCM để gửi thông báo tự động (Ví dụ: "Hộp sữa tươi của bạn sẽ hết hạn vào ngày mai!", hoặc "Ai đó vừa bình luận vào công thức của bạn").
