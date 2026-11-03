# Tài nguyên thực hành Apache JMeter

Trang HTML mẫu để sinh viên tải về, phục vụ bằng **Apache HTTP Server trên máy cá nhân** và gửi request từ Apache JMeter.

## Chuẩn bị

- Apache HTTP Server đã được cài đặt và khởi động được trên máy.
- Java và Apache JMeter đã được cài đặt.
- Git nếu tải bằng lệnh clone; có thể dùng **Code → Download ZIP** thay thế.

## Tải tài nguyên

```sh
git clone https://github.com/hoanghaitapcode/Mini_Exercise_Apache_Jmeter.git
```

Nếu đã clone, mở terminal trong thư mục repository rồi chạy `git pull` để lấy bản mới.

## Chạy bằng Apache HTTP Server local

1. Xác định thư mục **DocumentRoot** trong cấu hình Apache. Thư mục này thường có tên `htdocs`; vị trí thực tế phụ thuộc cách cài đặt.
2. Sao chép **toàn bộ thư mục `jmeter-lab`** trong repository vào DocumentRoot.
3. Khởi động Apache nếu chưa chạy.
4. Mở trình duyệt và truy cập:

```text
http://localhost/jmeter-lab/index.html
```

Ví dụ nếu DocumentRoot là `C:\Apache24\htdocs`, file sau khi sao chép phải nằm tại:

```text
C:\Apache24\htdocs\jmeter-lab\index.html
```

Trang hiển thị dòng **JMeter practice** khi thiết lập đúng.

Nếu Apache dùng port khác, thêm port vào URL, ví dụ:
`http://localhost:8080/jmeter-lab/index.html`.

Sau mỗi lần `git pull`, sao chép lại thư mục `jmeter-lab` vào DocumentRoot để cập nhật trang được Apache phục vụ.

## Thông tin kết nối từ JMeter

| Trường HTTP Request | Giá trị |
|---|---|
| Protocol | `http` |
| Server Name or IP | `localhost` |
| Port Number | `80`, hoặc port Apache thực tế |
| Method | `GET` |
| Path | `/jmeter-lab/index.html` |

Chuỗi có trong nội dung phản hồi: `JMeter practice`.

Ô Server Name or IP chỉ nhập `localhost`, không nhập cả URL. Sử dụng địa chỉ HTTP ở trên thay vì mở file bằng `file://`.

## Khắc phục nhanh

- **Connection refused:** kiểm tra Apache đã chạy và port đã đúng.
- **404 Not Found:** kiểm tra DocumentRoot, tên thư mục và đường dẫn file.
- **Apache không khởi động:** xem error log của Apache, kiểm tra port có đang được chương trình khác sử dụng.
- **Trang cũ vẫn xuất hiện:** kiểm tra đã sao chép bản mới vào đúng DocumentRoot; làm mới trình duyệt.

## Tài liệu

- [Apache HTTP Server — ánh xạ URL và DocumentRoot](https://httpd.apache.org/docs/2.4/urlmapping.html)
- [Apache JMeter — HTTP Request và các thành phần](https://jmeter.apache.org/usermanual/component_reference.html)
