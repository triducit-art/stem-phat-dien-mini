# STEM Power Lab – Chatbot trợ lý thiết kế mô hình phát điện mini

Công cụ HTML thuần chạy **hoàn toàn ngoại tuyến** cho học sinh THPT và giáo viên. Không yêu cầu tài khoản, API, hoặc cài đặt thư viện.

## Cách dùng

1. Mở `index.html` bằng Chrome, Edge hoặc Firefox.
2. Chọn nguồn phát (mặt trời, gió, nước, quay tay), tải, thời gian hoạt động, pin lưu trữ, vật liệu khung, ngân sách.
3. Nhấn **Phân tích & chọn vật tư** để xem công suất, năng lượng, nguồn gợi ý, danh mục vật tư và cảnh báo.
4. Đặt câu hỏi bằng tiếng Việt trong cửa sổ chat, ví dụ "Điện gió chạy quạt 5V cần những gì?", "Làm mạch dùng pin 18650 thế nào cho an toàn?".
5. Chọn **Xuất CSV** để lấy danh mục vật tư; **Tải phiếu dự án** để lấy văn bản; **In / lưu PDF** để in qua trình duyệt.

## Đưa lên GitHub Pages

Tạo repository mới hoặc dùng repository muốn triển khai, tải `index.html` vào thư mục gốc. Ở repository **Settings > Pages**, chọn **Deploy from a branch**, nhánh `main`, thư mục `/(root)` rồi lưu. Trang sẽ có địa chỉ `https://TEN-TAI-KHOAN.github.io/TEN-REPO/` khi GitHub Pages triển khai thành công. Có thể dùng GitHub Actions theo cài đặt của repository.

## Các công thức và giới hạn

- Công suất tải: `P = U × I × số tải` (W).
- Năng lượng: `E = P × thời gian` (Wh).
- Công suất nguồn gợi ý: tải có dự phòng và hệ số tổn thất DC-DC 85%; công cụ cũng áp dụng hệ số môi trường minh họa, không thay thế kiểm chứng theo đường đặc tính linh kiện. Khi có pin, nguồn được ước lượng theo cấp tải **hoặc** sạc bù riêng trong khoảng 3 giờ điều kiện thuận lợi, không được hiểu là bảo đảm vừa cấp tải vừa nạp nhanh cùng lúc.
- Dung lượng danh định một cell Li-ion: `3,7V × Ah`; năng lượng khai thác theo giả định 80% × 85%.
- Phương án phát từ gió, nước hoặc tay quay phụ thuộc tốc độ/lưu lượng, phải đo **V và I đồng thời khi mắc tải**.
- Chi phí chỉ là **giá giả định phục vụ bài học**; không phải báo giá thực tế.
- Chatbot dùng **quy tắc xử lý câu hỏi và công thức tính**, không phải mô hình ngôn ngữ AI hay ứng dụng gọi API.
- Sơ đồ là **sơ đồ khối**, không phải sơ đồ đấu chân từng mô-đun.

## An toàn

**Không dùng điện lưới 220V.** Nên dùng mô hình DC 3–12V, cách điện đúng cách, có công tắc và thiết bị bảo vệ. Với mô hình có cánh quay/nước, cần che chắn cơ khí và ngăn nước bắn vào điện.

**Pin 18650:** chỉ dùng cell có bảo vệ và bộ sạc Li-ion một cell tương thích loại nguồn, có quản lý chia sẻ nguồn/tải khi cần vừa sạc vừa chạy. Không dùng cell trần, không hàn trực tiếp vào cell, không tự ghép cell nối tiếp/song song, không sạc trực tiếp từ máy phát biến thiên, không sạc không giám sát. Giáo viên kiểm tra trước khi dùng.

Nguồn tham khảo:
- https://learn.adafruit.com/li-ion-and-lipoly-batteries/protection-circuitry
- https://learn.adafruit.com/usb-dc-and-solar-lipoly-charger/using-the-charger
- https://support.microbit.org/support/solutions/articles/19000101863-connecting-an-led-to-the-micro-bit

## Dữ liệu

Ứng dụng không truyền thông số học sinh lên máy chủ và không lưu thông tin cá nhân. Có thể sử dụng mở file HTML độc lập hoặc phục vụ qua GitHub Pages.
