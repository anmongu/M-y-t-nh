# ClassWiz 580 · Máy tính khoa học web

Ứng dụng HTML/CSS/JavaScript thuần, không gửi dữ liệu ra ngoài và không dùng `eval()`/`Function()`. Giao diện lấy Casio fx-580VN X làm tham chiếu; đây là công cụ độc lập, không phải firmware chính thức hoặc bản sao đã được CASIO chứng nhận.

## Chạy thử
- Mở `index.html` trong trình duyệt hiện đại để dùng Calculate. Một số trình duyệt hạn chế Service Worker trên `file://`.
- Để kiểm tra offline, phục vụ thư mục bằng máy chủ HTTP hoặc triển khai GitHub Pages, mở trang một lần khi có mạng, sau đó tải lại khi ngoại tuyến.
- Trang kiểm thử: `tests/runner.html`.

## Triển khai GitHub Pages
1. Tạo repository và tải toàn bộ nội dung thư mục này lên nhánh `main`.
2. Vào **Settings → Pages**.
3. Chọn **Deploy from a branch**, nhánh `main`, thư mục `/(root)`, rồi Save.
4. Mở URL Pages được GitHub cung cấp. Không đổi tên `index.html`, đường dẫn thư mục `src`, `styles` hoặc `manifest.json`.

## Chế độ hiện có
- **Calculate:** số học, lũy thừa, giai thừa, căn, sin/cos/tan, lượng giác ngược, sinh/cosh/tanh, log/ln, exp, làm tròn, biến Ans và góc DEG/RAD/GRAD.
- **Complex:** cộng, trừ, nhân, chia hai số phức dạng a+bi, môđun và argument.
- **Base-N:** chuyển đổi số nguyên giữa cơ số 2/8/10/16 trong giới hạn số nguyên an toàn của JavaScript.
- **Matrix:** hiển thị, chuyển vị, định thức và nghịch đảo ma trận vuông; kích thước tối đa 6×6.
- **Vector:** tích vô hướng, tích có hướng, độ lớn và góc giữa hai vectơ 3D.
- **Statistics:** n, tổng, trung bình, trung vị, phương sai/độ lệch chuẩn tổng thể và mẫu.
- **Distribution:** xấp xỉ xác suất tích lũy phân phối chuẩn.
- **Table:** bảng f(x) tối đa 101 dòng.
- **Equation/Func:** giải đa thức bậc hai và phương trình suy biến bậc nhất.
- **Inequality:** bất phương trình bậc nhất ax+b rel 0.
- **Verify:** so sánh giá trị số của hai biểu thức.
- **Ratio:** giải tỉ lệ a:b=c:x.

## Giới hạn đã biết
- Không tuyên bố tương đương hoàn toàn máy vật lý. Cách bố trí bàn phím, biểu diễn LCD và một số quy tắc khác với firmware gốc.
- Tính toán số học dùng IEEE-754 `Number`, không phải số học hữu tỉ chính xác hay số học độ chính xác cao. Số gần suy biến, số cực lớn/nhỏ và kết quả gần biên cần đối chiếu độc lập.
- Distribution hiện hỗ trợ phân phối chuẩn tích lũy bằng xấp xỉ erf, không bao gồm toàn bộ phân phối của model.
- Equation/Func chỉ giải phương trình bậc hai/bậc nhất; Inequality chỉ xử lý bậc nhất.
- Statistics chưa có hồi quy hai biến, bảng tần số hoặc trọng số.
- Spreadsheet không thuộc 12 chế độ gốc fx-580VN X và không được thêm vào menu.
- Bộ kiểm thử hiện tại không thay thế đối chiếu với máy fx-580VN X thật.

## Bảo mật và offline
Không có backend, đăng nhập, analytics hoặc API tính toán. Cài đặt/lịch sử lưu trong `localStorage` của trình duyệt. Service Worker cache các tệp cục bộ; khi phát hành phiên bản mới, đổi tên cache trong `service-worker.js` để kích hoạt cập nhật.

## Giấy phép
Xem `LICENSES.md`. Tên/model CASIO thuộc chủ sở hữu tương ứng; dự án này không được CASIO tài trợ hay chứng thực.
