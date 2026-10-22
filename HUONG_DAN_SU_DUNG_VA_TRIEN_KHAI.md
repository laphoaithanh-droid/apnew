# HỆ SINH THÁI HỌC TẬP THÍCH ỨNG LEARNMAP
## ĐƠN VỊ ĐĂNG KÝ: TRƯỜNG TIỂU HỌC HOÀI NHƠN (BÌNH ĐỊNH)
*Chuẩn Chương trình Giáo dục Phổ thông 2018 (GDPT 2018)*

---

## I. TỔNG QUAN HỆ THỐNG
Hệ sinh thái **LearnMap** được xây dựng dành riêng cho giáo viên, học sinh và phụ huynh **Trường Tiểu học Hoài Nhơn** với các tính năng đột phá:
1. **🔍 AI Diagnostic (Chẩn đoán & Quét lỗ hổng 5 phút):** Phân loại 3 nguyên nhân lỗi sai (Tính ẩu, Hổng lý thuyết gốc, Đọc hiểu đề kém) và lội ngược dòng kiểm tra đa tầng kiến thức (Lớp 5 → Lớp 4 → Lớp 2, 3).
2. **🗺️ AI Adaptive Learning Path (Bản đồ Lộ trình thích ứng):** Tự động rẽ nhánh bài học — học sinh yếu được học trực quan cắt bánh pizza/bánh chưng; học sinh giỏi được mở nhánh "Hack Não" Olympic.
3. **🎙️ AI Assistant (Trợ lý ảo giảng bài bằng giọng nói):** Voice AI đọc đề bài cho học sinh lớp 1, 2 và thư viện bài giảng hoạt họa ngắn gọn dưới 2 phút.
4. **📊 Đồng bộ Database Google Sheets Trực Tuyến:** Quản lý danh sách học sinh, điểm kinh nghiệm (XP), tinh thể Bio-Map và lịch sử học tập 2 chiều theo thời gian thực.
5. **🧮 Phòng Thí Nghiệm Toán Học Trực Quan (Math Lab):** Mô hình cắt bánh Pizza, vạch số phân số và Đấu trường Phép tính tính điểm.
6. **📄 Máy Tạo Phiếu Bài Tập & Đề Thi Phân Hóa:** Xuất file Word (`.doc`) chuẩn phông Times New Roman và in đề A4 kèm ma trận đề thi.

---

## II. HƯỚNG DẪN TRIỂN KHAI VÀ SỬ DỤNG TẠI TRƯỜNG

### Cách 1: Sử dụng Trực Tiếp Trên Máy Tính & Mạng Nội Bộ (LAN) của Trường (KHÔNG CẦN CÀI ĐẶT THÊM)
Máy chủ hiện tại đã được biên dịch và khởi chạy sẵn sàng:
1. **Chạy ngay bằng 1 click:** Nhấp đúp chuột vào tệp:
   ```
   d:\lop hoc\APPTO3\CHAY_APP_HOAI_NHON.bat
   ```
2. **Truy cập trên máy tính chính:**
   - Mở trình duyệt (Chrome, Cốc Cốc, Edge): `http://localhost:3000`
3. **Truy cập trên máy tính bảng, điện thoại hoặc máy tính phòng Tin học của trường:**
   - Đảm bảo thiết bị kết nối chung mạng Wi-Fi của trường.
   - Mở trình duyệt và gõ địa chỉ: `http://192.168.1.14:3000`

---

### Cách 2: Triển Khai Lên Mạng Internet (Truy cập mọi nơi 24/7 Miễn Phí)

#### 🔹 Lựa chọn 1: Triển khai lên Vercel (Khuyên dùng - Nhanh nhất)
1. Đăng ký tài khoản miễn phí tại [vercel.com](https://vercel.com).
2. Tải toàn bộ thư mục `APPTO3` lên GitHub hoặc dùng công cụ Vercel CLI:
   ```bash
   npm i -g vercel
   vercel
   ```
3. Vercel sẽ tự động phát hiện dự án Vite React và triển khai ra đường link công khai (ví dụ: `https://learnmap-hoai-nhon.vercel.app`).
4. Dự án đã được cấu hình sẵn tệp `vercel.json` định tuyến SPA chuẩn xác.

#### 🔹 Lựa chọn 2: Triển khai lên Render hoặc Railway (Dành cho bản Fullstack Node/Express)
1. Kết nối kho mã nguồn vào [render.com](https://render.com).
2. Cài đặt các thông số:
   - **Build Command:** `npm run build`
   - **Start Command:** `npm run start`
   - **Port:** `3000`
3. Ứng dụng sẽ chạy với địa chỉ web riêng của trường.

---

## III. HƯỚNG DẪN SỬ DỤNG CÁC TÍNH NĂNG CHÍNH

### 1. Kết Nối Google Sheets Của Trường Hoài Nhơn
1. Bấm vào biểu tượng **`Google Sheets`** ở góc phải thanh menu hoặc chân trang.
2. Dán đường link Google Sheet quản lý học sinh của trường vào ô cấu hình.
   *(Trường hợp chưa có trang tính, bấm **"Mẫu Google Sheet chuẩn"** để xem và sao chép cấu trúc mẫu 8 cột).*
3. Bật **"Tự động đồng bộ định kỳ"** (ví dụ mỗi 30 giây hoặc 1 phút). Mọi kết quả làm bài của học sinh sẽ tự động cập nhật về Google Sheet của trường.

### 2. Sử Dụng AI Chẩn Đoán Quét Lỗ Hổng 5 Phút (AI Diagnostic)
1. Bấm vào nút **`AI Chẩn Đoán (5p)`** trên thanh điều hướng.
2. Chọn khối lớp (Lớp 1 đến Lớp 5) và bấm **"Bắt đầu Chẩn đoán"**.
3. Học sinh tham gia trả lời các câu hỏi tình huống trong 5 phút.
4. Sau khi nộp bài:
   - AI chỉ rõ tỉ lệ lỗi sai: do **Tính toán ẩu**, **Không hiểu lý thuyết gốc** hay do **Đọc hiểu đề kém**.
   - Cây phả hệ tri thức hiển thị vị trí bị hổng ngược dòng (ví dụ hổng đặt tính lớp 4 hay bảng cộng lớp 2).
   - Bấm **"Kích hoạt Lộ trình Thích ứng"** để AI tự động vẽ bản đồ học riêng cho học sinh.

### 3. Bản Đồ Lộ Trình Thích Ứng (AI Adaptive Path)
1. Bấm vào nút **`Lộ Trình Thích Ứng`**.
2. Xem cây phân nhánh tự động:
   - Học sinh yếu sẽ thấy **Trạm Cứu Trợ Trực Quan** (cắt bánh Pizza, bánh Chưng). Bấm vào trạm để mở ngay phòng thí nghiệm mô phỏng.
   - Học sinh giỏi sẽ mở khóa các trạm **"Hack Não"** (Toán tư duy Kangaroo / Olympic).

### 4. Trợ Lý Ảo Giảng Bài Giọng Nói (AI Voice Assistant)
1. Bấm nút **`AI Giảng Bài Giọng Nói`** trên thanh menu hoặc nút **`Nghe AI đọc đề`** ở mỗi câu hỏi trong mục Khám phá.
2. Trợ lý ảo Voi Con Vui Vẻ sẽ đọc to, rõ ràng bằng giọng tiếng Việt thân thiện, diễn giải từng bước dưới 2 phút.

### 5. Xuất Đề Thi & Phiếu Bài Tập Ra File Word
1. Chuyển sang chế độ **"Giáo viên & Phụ huynh"**.
2. Bấm nút **`Tạo Đề Thi (Word)`**.
3. Chọn mức độ phân hóa học sinh (Học sinh Cần Bù Đắp Lỗ Hổng / Cơ Bản / Nâng Cao Vượt Trội).
4. Bấm **"Tải File Word (.doc)"** để lưu file về máy và in ấn trực tiếp cho học sinh làm bài trên lớp.

---

## IV. LIÊN HỆ & BẢO TRÌ HỆ THỐNG
- **Đơn vị vận hành:** Tổ Chuyên môn Toán - Tin & Ban Giám Hiệu Trường Tiểu học Hoài Nhơn
- **Phiên bản:** LearnMap Adaptive Learning Ecosystem v2.5 (GDPT 2018 Edition)
