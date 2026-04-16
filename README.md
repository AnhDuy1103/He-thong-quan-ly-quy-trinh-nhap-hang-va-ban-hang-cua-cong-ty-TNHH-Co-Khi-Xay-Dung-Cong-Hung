Hệ Thống Quản Lý Nhập & Bán Hàng (QLHANGHOA)
📖 Giới thiệu

Dự án xây dựng hệ thống quản lý quy trình nhập hàng và bán hàng cho Công ty TNHH Cơ khí Xây dựng Công Hùng.

Hệ thống hỗ trợ quản lý:

Nhà cung cấp
Khách hàng
Nhân viên
Hàng hóa
Hóa đơn nhập / bán
Công nợ
Giá bán (lẻ & sỉ)

Đây là project môn Quản trị Cơ sở dữ liệu, triển khai trên SQL Server.

🎯 Mục tiêu
Thiết kế CSDL từ Conceptual → Logical → Physical
Xây dựng hệ thống nhập – bán thực tế
Tự động hóa nghiệp vụ (tồn kho, công nợ, tính tiền,...)
Đảm bảo bảo mật & tính sẵn sàng
🧱 Kiến trúc hệ thống
1. Thực thể chính
NHA_CUNG_CAP
KHACH_HANG
NHAN_VIEN
HANG_HOA
2. Nghiệp vụ
Nhập hàng: NHAP, CT_NHAP
Bán hàng: BAN, CT_BAN
3. Công nợ
CONG_NO_NCC
CONG_NO_KH
4. Giá bán
GIA_BAN_LE
GIA_BAN_SI
⚙️ Chức năng chính
📥 Nhập hàng
Tạo hóa đơn nhập
Cập nhật tồn kho
Ghi nhận công nợ nhà cung cấp
📤 Bán hàng
Tạo hóa đơn bán
Áp dụng giá bán
Cập nhật tồn kho
Ghi nhận công nợ khách hàng
💰 Quản lý công nợ
Đã thanh toán
Thanh toán một phần
Chưa thanh toán
🤖 Tự động hóa
Tính THANHTIEN, TONGCONG, TONGTIEN
Cập nhật tồn kho tự động
Kiểm tra công nợ
🧪 Dữ liệu mẫu
EXEC Insert_NhaCungCap
EXEC Insert_NhanVien
EXEC Insert_KhachHang
EXEC Insert_HangHoa
EXEC Insert_GiaBanLe
EXEC Insert_GiaBanSi

📌 Dữ liệu được random gần với thực tế (tên, địa chỉ, SĐT)

🔐 Bảo mật
Phân quyền người dùng
Kiểm soát truy cập
Mã hóa dữ liệu
🛡️ Chống SQL Injection
Validate input
Dùng Stored Procedure
Kiểm tra dữ liệu đầu vào
♻️ Backup & High Availability
🔄 Backup
SQL Server Agent Job
Backup tự động
⚡ High Availability
Kế hoạch phục hồi dữ liệu
Giải pháp mở rộng khi dữ liệu lớn
🛠️ Công nghệ sử dụng
SQL Server
T-SQL (Stored Procedure, Trigger)
SQL Server Management Studio (SSMS)
🚀 Cách chạy dự án
1. Tạo database
CREATE DATABASE QLHANGHOA
GO
USE QLHANGHOA
2. Chạy file SQL tạo bảng
3. Sinh dữ liệu
EXEC Insert_NhaCungCap
EXEC Insert_NhanVien
EXEC Insert_KhachHang
EXEC Insert_HangHoa
4. Test
Nhập hàng
Bán hàng
Công nợ
Tồn kho
📂 Cấu trúc repo
QLHANGHOA/
│── database/
│   ├── schema.sql
│   ├── procedures.sql
│   └── triggers.sql
│
│── docs/
│   ├── ERD.png
│   └── report.pdf
│
│── README.md
✨ Điểm nổi bật
Thiết kế chuẩn 3NF
Mô phỏng nghiệp vụ thực tế
Tự động hóa mạnh (trigger + procedure)
Có bảo mật & backup
Có thể mở rộng dữ liệu lớn
👨‍💻 Nhóm thực hiện
Bùi Phương Chi
Nguyễn Ngọc Tuyết Nhi
Nguyễn Thị Tiến
Trương Huỳnh Thảo Ngân
Văn Công Anh Duy
