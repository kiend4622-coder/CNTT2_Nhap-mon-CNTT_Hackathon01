# BÀI LÀM – HACKATHON 01

- **Mã đề:** 17
- **Họ tên:**ĐỖ TRUNG KIÊN
- **Lớp:** CNTT2
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** WINDOW

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng
pwd
ls -force
mv '.\Nguon Hang.txt' .\docs\
mv .\logo_trai_cay_sạch.png .\media\
rm .\temp_252.tmp
cd .\logs\
ls
cd ..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
 Directory: C:\Users\do trung kien\Downloads\starter-kit\starter-kit\trai-cay-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026   1:44 PM                backup
d-----        10/28/2026   1:45 PM                data
d-----        10/28/2026   1:52 PM                docs
d-----        10/28/2026   1:49 PM                logs
d-----        10/28/2026   1:54 PM                media
------        10/27/2026   1:32 AM             70 .env
------        10/27/2026   1:32 AM           2228 bai_lam.md


    Directory: C:\Users\do trung kien\Downloads\starter-kit\starter-kit\trai-cay-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           6095 ban_trai_cay_thang_7.xlsx


    Directory: C:\Users\do trung kien\Downloads\starter-kit\starter-kit\trai-cay-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM             66 Nguon Hang.txt


    Directory: C:\Users\do trung kien\Downloads\starter-kit\starter-kit\trai-cay-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/28/2026   1:49 PM            584 daily_report.txt
-a----        10/27/2026   1:32 AM           1041 fruit.log


    Directory: C:\Users\do trung kien\Downloads\starter-kit\starter-kit\trai-cay-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           7054 logo_trai_cay_sạch.png
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
# Ghi lệnh vào đây (xoá dòng này)
gc .\logs\fruit.log |Select-String "ERROR"
gc .\logs\fruit.log |Select-String "ERROR" >> .\logs\daily_report.txt
gc .\logs\daily_report.txt
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-07-28 09:31:32 [ERROR] Thanh toan bi tu choi
2026-07-28 09:40:32 [ERROR] Het thoi gian cho (timeout)
```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Ghi lệnh vào đây (xoá dòng này)
ni .\logs\autoreport.txt
gc .\logs\fruit.log |Select-String "ERROR" >> .\logs\autoreport.txt
start .\logs\autoreport.txt
```

### Kết quả hiển thị

```text
(Dán kết quả vào đây – xoá dòng này)
2026-07-28 09:31:32 [ERROR] Thanh toan bi tu choi
2026-07-28 09:40:32 [ERROR] Het thoi gian cho (timeout)
2026-07-28 09:49:32 [ERROR] Khong tim thay trang /hang-moi-ve (404)
2026-07-28 10:04:32 [ERROR] Thanh toan bi tu choi
2026-07-28 10:16:32 [ERROR] Het thoi gian cho (timeout)



```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
 (gc .\logs\autoreport.txt | Select-String "ERROR").count
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
6
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
ni .\logs\tong_hop.txt
set-content .\logs\tong_hop.txt -value "===TONG HOP LOG==="
gc .\logs\fruit.log | Select-String "WARNING" >> .\logs\tong_hop.txt
``` 

### Nội dung file logs/tong_hop.txt

```text

===TONG HOP LOG===

 
 2 0 2 6 - 0 7 - 2 8   0 9 : 3 7 : 3 2   [ W A R N I N G ]   D o n   g i a o   t r o n g   g i o   c a o   d i e m 
 
 2 0 2 6 - 0 7 - 2 8   1 0 : 0 7 : 3 2   [ W A R N I N G ]   D o n   g i a o   t r o n g   g i o   c a o   d i e m 
 
 2 0 2 6 - 0 7 - 2 8   1 0 : 1 3 : 3 2   [ W A R N I N G ]   D o n   g i a o   t r o n g   g i o   c a o   d i e m 
 
 
 
 
 
 
```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/ban_trai_cay_thang_7.xlsx`, không cần ghi vào đây.
