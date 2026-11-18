# BÁO CÁO KẾT THÚC HỌC PHẦN LẬP TRÌNH .NET

## ĐỀ TÀI: XÂY DỰNG PHẦN MỀM QUẢN LÝ KÝ TÚC XÁ

- **Giảng viên hướng dẫn:** ThS. Cấn Đức Điệp
- **Lớp:** D19CNPM3
- **Nhóm thực hiện:** 18

| Thành viên | MSSV |
|---|---|
| Phạm Hữu Hưng | 24810310239 |
| Nguyễn Xuân An | 24810310247 |

---

## 1. Giới thiệu đề tài

Hệ thống Quản lý Ký túc xá là phần mềm desktop xây dựng trên nền tảng .NET, hỗ trợ Ban quản lý ký túc xá tối ưu hóa quy trình làm việc. Hệ thống giúp số hóa các thao tác thủ công, giảm sai sót trong lưu trữ hồ sơ, đồng thời minh bạch hóa quá trình tính toán chi phí lưu trú của sinh viên.

### Các tính năng cốt lõi

- Quản lý danh mục cơ sở vật chất (tòa nhà, phòng, loại phòng, giường)
- Quản lý thông tin và hồ sơ nội trú của sinh viên
- Xử lý nghiệp vụ phân phòng (check-in) và trả phòng (check-out)
- Quản lý số điện, nước tiêu thụ hàng tháng
- Tự động tính toán, phát sinh hóa đơn và quản lý trạng thái thanh toán
- Đăng nhập, phân quyền và quản lý tài khoản cán bộ

### Công nghệ sử dụng

| Thành phần | Công nghệ |
|---|---|
| Ngôn ngữ | C# |
| Giao diện | Windows Forms |
| Cơ sở dữ liệu | Microsoft SQL Server |
| Kiến trúc | 3 lớp (GUI – BUS – DAL) |
| Quản lý mã nguồn | Git & GitHub |

---

## 2. Phân chia công việc

Dự án do 2 thành viên thực hiện, khối lượng công việc được chia đều theo các module nghiệp vụ.

### Thành viên 1: Nguyễn Xuân An (24810310247)

**Module Quản lý Danh mục & Lưu trú (Core Data & Placement)**

- **Thiết kế database (làm chung):** lên sơ đồ CSDL, tạo bảng và khóa
- **Quản lý tòa nhà và phòng:**
  - Thêm, sửa, xóa thông tin tòa nhà, loại phòng, giá phòng
  - Thiết lập logic quản lý số giường trống trong mỗi phòng
- **Quản lý hồ sơ sinh viên:** quản lý thông tin cá nhân của sinh viên đăng ký nội trú
- **Nghiệp vụ xếp/trả phòng:**
  - Check-in: chỉ cho phép thêm sinh viên vào phòng còn giường, tự động trừ số giường trống
  - Check-out: xóa sinh viên khỏi phòng, tự động cộng lại số giường trống

### Thành viên 2: Phạm Hữu Hưng (24810310239)

**Module Dịch vụ, Tài chính & Hệ thống (Operations & Billing)**

- **Thiết kế database (làm chung):** lên sơ đồ CSDL, tạo bảng và khóa
- **Module hệ thống:** đăng nhập, đăng xuất, quản lý tài khoản cán bộ nhân viên
- **Quản lý điện và nước:** ghi nhận và tính toán số điện, số nước tiêu thụ hàng tháng cho từng phòng
- **Quản lý hóa đơn và thanh toán (Core):**
  - Tự động phát sinh hóa đơn tổng hợp (tiền phòng + tiền điện + tiền nước) hàng tháng
  - Cập nhật trạng thái thanh toán (đã thu / còn nợ)
  - Thống kê doanh thu cơ bản theo tháng

---

## 3. Cấu trúc thư mục

```
BC.NET_QuanLyKTX/
├── Database/
│   └── QuanLyKTX.sql       # Script tạo database + dữ liệu mẫu
├── GUI/                    # Các form giao diện
├── BUS/                    # Xử lý nghiệp vụ
├── DAL/                    # Truy cập dữ liệu
├── DTO/                    # Các lớp đối tượng
├── docs/                   # Báo cáo, use case, ERD
├── .gitignore
└── README.md
```

---

## 4. Hướng dẫn cài đặt và chạy thử

1. Clone repository về máy:
   ```
   git clone https://github.com/hung-30/BC.NET_QuanLyKTX.git
   ```
2. Mở SQL Server Management Studio, chạy file `Database/QuanLyKTX.sql` để khởi tạo database và dữ liệu mẫu.
3. Mở file solution (`.sln`) bằng Visual Studio.
4. Cập nhật chuỗi kết nối (Connection String) tới SQL Server của máy bạn trong file `App.config`.
5. Build và chạy dự án (F5).

### Tài khoản mặc định

| Vai trò | Tên đăng nhập | Mật khẩu |
|---|---|---|
| Admin | `admin` | `admin123` |
| Quản lý | `quanly1` | `quanly123` |

---

## 5. Quy ước làm việc nhóm

- Không code trực tiếp trên `main`; mỗi người làm trên nhánh riêng
- Merge về `main` qua Pull Request, khoảng 2–3 ngày một lần
- Mỗi người chỉ sửa form thuộc module của mình; sửa phần dùng chung phải báo nhau trước
- Mọi thay đổi database phải cập nhật vào `Database/QuanLyKTX.sql`
