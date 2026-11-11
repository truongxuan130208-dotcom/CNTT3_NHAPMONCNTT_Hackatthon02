# BÀI LÀM – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:pham xuan truong**
- **Lớp:CNTT3**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -force
 mv .\lich_lam_viec.txt .\docs\
mkdir backup
cp .\data\hoa_don_spa_thang_7.xlsx .\backup\
 rm .\temp_707.tmp
 ls -Force
Get-ChildItem -Recurse -Force
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  10:45 AM                data
d-----        11/11/2026  10:44 AM                docs
d-----        11/11/2026  10:44 AM                evidence
d-----        11/11/2026  10:45 AM                logs
d-----        11/11/2026  10:42 AM                web
------         11/3/2026   7:07 AM             75 .env
-a----         11/3/2026   7:07 AM            149 lich_lam_viec.txt
------         11/3/2026   7:07 AM             22 temp_707.tmp


    Directory: C:\Users\tTRUONG\Downloads\starter-kit (2)\starter-kit\spa-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: C:\Users\tTRUONG\Downloads\starter-kit (2)\starter-kit\spa-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            939 service.log


    Directory: C:\Users\tTRUONG\Downloads\starter-kit (2)\starter-kit\spa-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  10:42 AM                images
------         11/3/2026   7:07 AM            597 app.js
------         11/3/2026   7:07 AM            523 index.html
------         11/3/2026   7:07 AM            460 style.css


    Directory: C:\Users\tTRUONG\Downloads\starter-kit (2)\starter-kit\spa-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
------         11/3/2026   7:07 AM           3091 logo-lotuscare.png```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
gc .\logs\service.log |Select-String "status" > .\logs\loi_500.txt
```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-07-28 08:03:17 GET /css/style.css status=200
2026-07-28 08:05:28 GET / status=200

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
 (gc .\logs\service.log |Select-String "status=404").count
```

```text
4
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
 Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
 .\tong_hop.ps1```

### Nội dung file logs/tong_hop.txt

```text
Dang tao bao cao...
Hoan thanh!
```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | network |lỗi không hiển thị hình ảnh  | vào index.html mở VS studio code tại dòng 10 đổi tên thành <img src="images/logo-lotuscare.png" alt="Logo" class="logo"> |
| 2 | console | lỗi không hiển thị bảng giá | vào app.js tại dòng cuối đổi thành hienThiGoiSpa();
 |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:Tôi là sinh viên năm nhất chưa biết fix lỗi bảng bao giờ** 
- **Expected:website của tôi bị lỗi bảng** 
- **Actual:bảng của tôi bị lỗi như này "Uncaught ReferenceError"** 
- **Log:"Uncaught ReferenceError"** 

### Câu tìm kiếm Google

```text
site:stackoverfolow.com "Uncaught ReferenceError"
```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_spa_thang_7.xlsx`, không cần ghi vào đây.
