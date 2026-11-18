# BÁO CÁO KẾT THÚC HỌC PHẦN LẬP TRÌNH .NET
---

## ĐỂ TÀI: XÂY DỰNG PHẦN MỀM QUẢN LÝ KTX
---

- **Giảng viên hướng dẫn:** THS.CẤN ĐỨC ĐIỆP
- **Nhóm thực hiện:** 18

---

### 📖 1. Giới thiệu đề tài

Hệ thống Quản lý Ký túc xá là một phần mềm được xây dựng trên nền tảng .NET nhằm hỗ trợ Ban quản lý ký túc xá tối ưu hóa quy trình làm việc. Hệ thống giúp số hóa các thao tác thủ công, giảm thiểu sai sót trong việc lưu trữ hồ sơ, đồng thời minh bạch hóa quá trình tính toán chi phí lưu trú của sinh viên.

Các tính năng cốt lõi (Core Features):

Quản lý danh mục cơ sở vật chất (Tòa nhà, Phòng ban).

Quản lý thông tin và hồ sơ nội trú của Sinh viên.

Xử lý nghiệp vụ phân phòng (Check-in) và trả phòng (Check-out).

Quản lý số điện, nước tiêu thụ hàng tháng.

Tự động tính toán, phát sinh hóa đơn và quản lý trạng thái thanh toán.

Công nghệ sử dụng:

Ngôn ngữ: C#

Giao diện	Windows Forms

Cơ sở dữ liệu: Microsoft SQL Server

Công cụ quản lý source code: Git & GitHub

### 👥 2. Phân chia công việc 

Dự án được thực hiện bởi 2 thành viên, với khối lượng công việc được chia đều dựa trên các module nghiệp vụ như sau:

#### 🧑‍💻 Thành viên 1: Nguyễn Xuân An - 24810310247

Đảm nhiệm Module Quản lý Danh mục & Lưu trú (Core Data & Placement)

Thiết kế Database (Làm chung): Lên sơ đồ CSDL, tạo bảng và khóa.

Quản lý Tòa nhà & Phòng: Thêm/sửa/xóa thông tin tòa nhà, loại phòng, giá phòng. Thiết lập logic quản lý số lượng giường trống trong mỗi phòng.

Quản lý Hồ sơ Sinh viên: Quản lý thông tin cá nhân của sinh viên đăng ký nội trú.

Nghiệp vụ Xếp/Trả phòng:

Xử lý logic Check-in (chỉ cho phép thêm SV vào phòng còn giường, tự động trừ số giường trống).

Xử lý logic Check-out (xóa SV khỏi phòng, tự động cộng lại số giường trống).

#### 🧑‍💻 Thành viên 2: Phạm Hữu Hưng - 24810310239

Đảm nhiệm Module Dịch vụ, Tài chính & Hệ thống (Operations & Billing)

Thiết kế Database (Làm chung): Lên sơ đồ CSDL, tạo bảng và khóa.

Module Hệ thống: Lập trình chức năng Đăng nhập, Đăng xuất, và quản lý tài khoản của cán bộ nhân viên.

Quản lý Điện & Nước: Xây dựng chức năng ghi nhận và tính toán số điện, số nước tiêu thụ hàng tháng cho từng phòng.

Quản lý Hóa đơn & Thanh toán (Core):

Tự động phát sinh hóa đơn tổng hợp (Tiền phòng + Tiền điện + Tiền nước) hàng tháng.

Cập nhật trạng thái thanh toán (Đã thu / Còn nợ).

Thống kê doanh thu cơ bản theo tháng.

### 3. Cấu trúc thư mục
BC_LT.NET/
├── database/
│   └── QuanLyKTX.sql        # Script tạo database + dữ liệu mẫu
├── GUI/                     # Các form giao diện
├── BLL/                     # Xử lý nghiệp vụ
├── DAL/                     # Truy cập dữ liệu
├── DTO/                     # Các lớp đối tượng
├── docs/                    # Báo cáo, use case, ERD
├── .gitignore
└── README.md

### 🚀 4. Hướng dẫn cài đặt và chạy thử

Clone repository này về máy tính: git clone (https://github.com/hung-30/BC.NET_QuanLyKTX.git)

Mở file script SQL [Tên file database].sql trong thư mục Database và chạy trong SQL Server để khởi tạo dữ liệu.

Mở Solution bằng Visual Studio.

Cập nhật lại chuỗi kết nối (Connection String) tới SQL Server của bạn tại file [App.config hoặc appsettings.json].

Build và Run dự án.
