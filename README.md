📦 Hệ Thống Quản Lý Nhập & Bán Hàng (QLHANGHOA)
📌 Giới thiệu

Dự án xây dựng hệ thống quản lý quy trình nhập hàng và bán hàng cho Công ty TNHH Cơ khí Xây dựng Công Hùng.
Hệ thống được thiết kế nhằm hỗ trợ quản lý:

Nhà cung cấp
Khách hàng
Nhân viên
Hàng hóa
Hóa đơn nhập / bán
Công nợ
Giá bán (lẻ & sỉ)

Đây là project thuộc môn Quản trị Cơ sở dữ liệu, tập trung vào thiết kế, triển khai và tối ưu hệ thống database trên SQL Server.

🎯 Mục tiêu
Thiết kế cơ sở dữ liệu đầy đủ từ conceptual → logical → physical
Xây dựng hệ thống quản lý nhập – bán thực tế
Tự động hóa các nghiệp vụ (tồn kho, công nợ, tính tiền,…)
Đảm bảo bảo mật & tính sẵn sàng của hệ thống
🧱 Kiến trúc hệ thống
1. Các thực thể chính
NHA_CUNG_CAP
KHACH_HANG
NHAN_VIEN
HANG_HOA
2. Nghiệp vụ chính
Nhập hàng:
NHAP, CT_NHAP
Bán hàng:
BAN, CT_BAN
3. Quản lý tài chính
CONG_NO_NCC – Công nợ nhà cung cấp
CONG_NO_KH – Công nợ khách hàng
4. Quản lý giá
GIA_BAN_LE
GIA_BAN_SI
🗄️ Thiết kế cơ sở dữ liệu
🔹 Mức khái niệm
Xây dựng ERD từ hóa đơn nhập và hóa đơn bán
Xác định thực thể, thuộc tính, mối quan hệ
🔹 Mức logic

Chuẩn hóa dữ liệu:

Tách bảng chi tiết (CT_NHAP, CT_BAN)
Tách bảng công nợ
Đảm bảo chuẩn hóa (3NF)
🔹 Mức vật lý
Sử dụng SQL Server
Áp dụng:
Primary Key
Foreign Key
Check Constraint
Unique Constraint
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
Theo dõi:
Đã thanh toán
Thanh toán một phần
Chưa thanh toán
📊 Tự động xử lý
Tính:
Thành tiền
Tổng cộng
Tổng tiền
Kiểm tra khách hàng có nợ
Cập nhật tồn kho tự động
🧪 Dữ liệu mẫu (Data Generation)

Sử dụng Stored Procedure để sinh dữ liệu:

Insert_NhaCungCap (~200 NCC)
Insert_NhanVien (~50 NV)
Insert_KhachHang (lớn, mô phỏng thực tế)
Insert_HangHoa (~100 sản phẩm)
Insert_GiaBanLe, Insert_GiaBanSi

👉 Dữ liệu được random gần với thực tế (địa chỉ, số điện thoại, tên…)

🔐 Bảo mật hệ thống
Áp dụng:
Phân quyền người dùng
Kiểm soát truy cập
Mã hóa dữ liệu
Giám sát hoạt động
Chống SQL Injection:
Validate input
Sử dụng stored procedures
Kiểm tra dữ liệu đầu vào
♻️ Backup & High Availability
Backup
Thiết lập SQL Server Agent Job
Backup tự động theo lịch
Đảm bảo hoạt động 24/7
Kế hoạch phục hồi dữ liệu
Giải pháp mở rộng lưu trữ (khi dữ liệu lớn)
🛠️ Công nghệ sử dụng
SQL Server
T-SQL (Stored Procedure, Trigger)
SQL Server Management Studio (SSMS)
🚀 Cách chạy dự án
Tạo database:
CREATE DATABASE QLHANGHOA
Chạy file SQL để tạo bảng
Chạy các stored procedure để sinh dữ liệu:
EXEC Insert_NhaCungCap
EXEC Insert_NhanVien
EXEC Insert_KhachHang
EXEC Insert_HangHoa
Test các chức năng:
Nhập hàng
Bán hàng
Công nợ
Tồn kho
📌 Điểm nổi bật
Thiết kế database chuẩn bài bản
Mô phỏng nghiệp vụ thực tế
Tự động hóa mạnh (trigger/procedure)
Có đầy đủ:
Bảo mật
Backup
Khả năng mở rộng
👨‍💻 Nhóm thực hiện
Bùi Phương Chi
Nguyễn Ngọc Tuyết Nhi
Nguyễn Thị Tiến
Trương Huỳnh Thảo Ngân
Văn Công Anh Duy
