# 🏗️ Hệ Thống Quản Trị CSDL & Công Nợ - Công Ty Cơ Khí Xây Dựng Công Hùng

![SQL Server](https://img.shields.io/badge/Database-SQL%20Server-red?style=for-the-badge&logo=microsoft-sql-server)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![University](https://img.shields.io/badge/University-DUE-blue?style=for-the-badge)

[cite_start]Dự án cuối kỳ môn **Quản trị Cơ sở Dữ liệu** thực hiện tại Khoa Thống kê – Tin học, Trường Đại học Kinh tế - ĐHĐN[cite: 1, 2, 5]. [cite_start]Hệ thống tập trung vào việc số hóa quy trình vận hành kho, quản lý giá bán linh hoạt và kiểm soát rủi ro tài chính thông qua công nợ[cite: 7].

---

## 📖 Mục lục
- [Tổng quan dự án](#-tổng-quan-dự-án)
- [Kiến trúc dữ liệu](#-kiến-trúc-dữ-liệu)
- [Các tính năng cốt lõi](#-các-tính-năng-cốt-lõi)
- [Kỹ thuật lập trình CSDL](#-kỹ-thuật-lập-trình-csdl)
- [Hướng dẫn cài đặt](#-hướng-dẫn-cài-đặt)
- [Thành viên thực hiện](#-thành-viên-thực-hiện)

---

## 🎯 Tổng quan dự án
[cite_start]Hệ thống được thiết kế riêng cho **Công ty TNHH Cơ khí Xây dựng Công Hùng** để quản lý quy trình nhập và bán hàng[cite: 7, 8]. Dự án giải quyết các vấn đề thực tế như:
* [cite_start]Tự động hóa tính toán tồn kho thời gian thực[cite: 1350].
* [cite_start]Áp dụng chính sách giá sỉ/lẻ tự động theo số lượng mua[cite: 1573, 1574].
* [cite_start]Ràng buộc điều kiện bán hàng dựa trên lịch sử nợ của khách hàng[cite: 2220, 2221].

## 🛠️ Kiến trúc dữ liệu
[cite_start]Dữ liệu được chuẩn hóa để đảm bảo tính toàn vẹn và tối ưu hiệu năng[cite: 76]:
* [cite_start]**Thiết kế mức khái niệm**: Sơ đồ ERD tích hợp quy trình nhập và bán[cite: 72, 75].
* [cite_start]**Chuẩn hóa**: Các quan hệ được đưa về dạng chuẩn để loại bỏ dư thừa[cite: 86, 90].
* [cite_start]**Thực thể chính**: `NHA_CUNG_CAP`, `NHAN_VIEN`, `KHACH_HANG`, `HANG_HOA`, `NHAP`, `BAN`, `CONG_NO`[cite: 78, 79, 80, 81, 84, 85, 89, 93].

## 🚀 Các tính năng cốt lõi

### 1. Quản lý kho tự động
* [cite_start]Sử dụng **Triggers** để cập nhật tồn kho ngay khi phát sinh giao dịch nhập/xuất[cite: 1367, 1423].
* [cite_start]Tự động in cảnh báo khi tồn kho của một mặt hàng xuống dưới ngưỡng an toàn (200 đơn vị)[cite: 1454, 1461].

### 2. Công cụ tính giá thông minh
* [cite_start]Tự động xác định đơn giá phù hợp cho chi tiết hóa đơn dựa trên số lượng mua (Bán lẻ hoặc Bán sỉ 3 mức: 50, 100, 500 đơn vị) [cite: 1639-1670].
* [cite_start]Kiểm tra hiệu lực của bảng giá theo thời gian đảm bảo tính chính xác tại thời điểm lập hóa đơn[cite: 1643, 1651, 1659, 1667].

### 3. Kiểm soát nợ xấu (Debt Policy)
* [cite_start]**Trigger chặn hóa đơn**: Nếu khách hàng chưa thanh toán hết nợ cũ hoặc nợ quá hạn, hệ thống sẽ từ chối tạo hóa đơn bán mới trừ khi đã thanh toán ít nhất 50% [cite: 2221, 2243-2293].
* [cite_start]Tự động đẩy dữ liệu vào bảng công nợ khi hình thức thanh toán của hóa đơn là ghi nợ (HTTT IS NULL)[cite: 1471, 1522].

## 💻 Kỹ thuật lập trình CSDL

### Xử lý dữ liệu quy mô lớn (Big Data Mockup)
Dự án bao gồm các **Stored Procedures** tối ưu để khởi tạo hàng triệu bản ghi mẫu nhằm kiểm thử hiệu năng:
* [cite_start]`Insert_KhachHang`: Khởi tạo **1.000.000** khách hàng với thông tin địa chỉ Việt Nam chuẩn [cite: 526, 567-569].
* [cite_start]`Insert_Ban`: Khởi tạo **1.000.000** hóa đơn bán hàng[cite: 1097].
* [cite_start]`Insert_Nhap`: Khởi tạo **1.000.000** hóa đơn nhập hàng[cite: 855].

### Logic nghiệp vụ phức tạp
* [cite_start]Tự động tính toán `THANHTIEN`, `TONGCONG`, và `TONGTIEN` (bao gồm thuế GTGT) thông qua Trigger khi có bất kỳ thay đổi nào ở bảng chi tiết [cite: 2068-2070, 2140-2141].

## 📂 Hướng dẫn cài đặt
1. Clone repository về máy.
2. Mở SQL Server Management Studio (SSMS).
3. [cite_start]Chạy lệnh tạo Database: `CREATE DATABASE QLHANGHOA;`[cite: 118].
4. [cite_start]Thực thi các script SQL theo thứ tự: cấu trúc bảng, trigger nghiệp vụ, và cuối cùng là procedure tạo dữ liệu[cite: 120, 1348, 238].

## 👥 Thành viên thực hiện
* [cite_start]**Bùi Phương Chi** [cite: 11]
* [cite_start]**Nguyễn Ngọc Tuyết Nhi** [cite: 12]
* [cite_start]**Nguyễn Thị Tiến** [cite: 13]
* [cite_start]**Trương Huỳnh Thảo Ngân** [cite: 14]
* [cite_start]**Văn Công Anh Duy** [cite: 15]

---
[cite_start]*Dự án thuộc học phần Quản trị Cơ sở dữ liệu - Đà Nẵng, 03/2025*[cite: 16].
