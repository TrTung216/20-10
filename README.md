# Chút thương · Thiệp 20/10

Trang thiệp chúc mừng ngày Phụ nữ Việt Nam dành cho bạn bè, bằng tiếng Việt.

## Tính năng

- Thiệp giấy màu kem, hoa tulip vẽ bằng SVG và hiệu ứng mở thư.
- Điền tên người nhận, tên người gửi, lời chúc riêng hoặc chọn 3 mẫu.
- Tạo link cá nhân hóa; người nhận mở link sẽ thấy thiệp, không thấy biểu mẫu.
- Link gọn hơn: lời chúc mẫu dùng mã mẫu, lời chúc riêng dùng UTF-8/Base64URL và nén Deflate khi có lợi. Các link cũ vẫn mở được.
- Giao diện điện thoại, hỗ trợ bàn phím và chế độ giảm chuyển động.
- HTML/CSS/JavaScript thuần, không cần cài thư viện, không dùng dịch vụ bên ngoài.

## Xem trên máy

Mở `index.html` bằng trình duyệt. Chức năng gửi link cần trang được host bằng HTTPS.

## Xuất bản bằng GitHub Pages

Trong repository, mở **Settings → Pages → Build and deployment**:

1. Chọn **Deploy from a branch**.
2. Chọn nhánh chứa `index.html` (thường là `main`), thư mục **/ (root)**.
3. Nhấn **Save**, chờ GitHub hoàn tất triển khai.

Địa chỉ dự kiến: https://trtung216.github.io/20-10/

## Cách gửi

Nhập tên và lời chúc → nhấn **Tạo link & gửi yêu thương** → dán link vào tin nhắn.
Nếu trình duyệt không cho sao chép tự động, sao chép link trong ô hiện ra.

Tên và lời chúc được mã hóa URL trong phần fragment (`#`) của link, không lưu vào cơ sở dữ liệu. Đây không phải mã hóa bảo mật: ai có link đều đọc được. Không đưa thông tin nhạy cảm vào thiệp.

Link mới dùng định dạng `v1` (Base64URL) hoặc `z1` (Deflate + Base64URL). Link `z1` cần trình duyệt hỗ trợ `DecompressionStream`; nếu trình duyệt tạo thiệp không hỗ trợ nén, web tự dùng `v1`. Nội dung ba mẫu lời chúc ở phiên bản 1 phải được giữ nguyên để các link đã gửi không đổi nội dung. Muốn link có độ dài cố định rất ngắn cần thêm dịch vụ lưu thiệp hoặc rút gọn URL.

## Chỉnh sửa

Toàn bộ giao diện và logic nằm trong `index.html`. Sửa biến `wishes` để thay lời chúc mẫu, biến CSS `:root` để thay bảng màu.