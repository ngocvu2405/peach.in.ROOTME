## Link challenge: [SQL injection - Authentication](https://www.root-me.org/en/Challenges/Web-Server/SQL-injection-authentication)

Ta sẽ injection vào query ở mục đăng nhập. Ta thử một chút: `administrator' OR 1=1--` với password tuỳ ý. Ta có:

![img1](https://i.imgur.com/RpQsNYe.png)

Có lẽ query phía sau nếu được trả về sẽ vẽ ra thêm 1 khung đăng nhập nữa đã fill

Giờ ta check số cột sẽ được trả về bằn payload" `'ORDER BY 3--` và đứng như dự đoán, chỉ có 2 cột được trả về.

![img2](https://i.imgur.com/QVWTK7o.png)

Nhìn lỗi ta cũng biết thêm rằng SQLite3 được sử dụng cho database của trang web. Ta kiếm thông tin về table thông qua sqlite_master bằng query `'UNION SELECT name, sql FROM sqlite_master--`

![img3](https://i.imgur.com/lOf2E7v.png)

Từ đó, ta biết được có bảng `users` và bảng gồm các cột `usename, password, year`

Truy vấn lấy dữ liệu từ bảng này qua query: `'UNION SELECT username, password FROM user--`

![img4](https://i.imgur.com/ooddSoP.png)

Thế là DONE!