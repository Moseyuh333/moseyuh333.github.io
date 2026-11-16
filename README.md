# Hướng dẫn Deploy Portfolio lên Cloudflare Pages (Miễn phí 100%)

Cách nhanh nhất và tiện nhất để giữ tên miền `moseyuh333.loc.cc` luôn **Healthy** mà không tốn 1 xu là dùng **Cloudflare Pages**.

---

### Bước 1: Deploy lên Cloudflare Pages (Không cần Git)

1. Truy cập [dash.cloudflare.com](https://dash.cloudflare.com) và đăng nhập (hoặc đăng ký tài khoản miễn phí).
2. Vào mục **Compute (Workers & Pages)** -> chọn tab **Pages**.
3. Bấm **Create application** -> Chọn tab **Upload assets** (Direct Upload).
4. Đặt tên dự án (ví dụ: `moseyuh-portfolio`).
5. Kéo thả toàn bộ thư mục `portfolio-moseyuh333` (chứa `index.html`, `style.css`, `script.js`) vào ô tải lên.
6. Bấm **Deploy site**.
7. Chờ vài giây, bạn sẽ nhận được một địa chỉ web miễn phí dạng:  
   👉 `moseyuh-portfolio.pages.dev`

---

### Bước 2: Gắn Custom Domain `moseyuh333.loc.cc`

1. Tại trang quản lý dự án vừa tạo trên Cloudflare Pages, chọn tab **Custom domains**.
2. Bấm **Set up a custom domain**.
3. Nhập tên miền của bạn: `moseyuh333.loc.cc` -> Bấm **Continue**.
4. Cloudflare sẽ thông báo yêu cầu trỏ CNAME về `moseyuh-portfolio.pages.dev`.

---

### Bước 3: Cấu hình DNS trên Yunamo (`loc.cc`)

1. Mở lại trang quản lý DNS của `moseyuh333.loc.cc` (nơi đang báo *No records found*).
2. Bấm **Add Record** (Thêm bản ghi):
   - **Type (Loại)**: `CNAME`
   - **Name (Tên / Host)**: `@` (hoặc để trống, tùy giao diện)
   - **Target / Value (Giá trị)**: `moseyuh-portfolio.pages.dev`
   - **TTL**: `1h` (hoặc Auto)
3. Lưu bản ghi lại.

---

### Kết quả:
- Cloudflare Pages sẽ tự động cấp phát SSL miễn phí cho `moseyuh333.loc.cc`.
- Khi truy cập `moseyuh333.loc.cc`, trang web portfolio sẽ hiển thị ngay lập tức.
- Ở lần quét Health Check tiếp theo trên Yunamo, các chỉ số:
  - **DNS Status**: `passed` ✅
  - **HTTP Status**: `online` ✅
  - **SSL Status**: `valid` ✅
  - **Overall Health**: `Healthy` ✅
