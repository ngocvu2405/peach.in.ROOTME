## Link challenge: [SQL Injection -Blind](https://www.root-me.org/en/Challenges/Web-Server/SQL-injection-Blind)

Ở challenge này, chúng ta áp dụng SQL Injection vào khung login. 
Ta thử injection thì ta dễ dàng tìm thấy câu truy vấn này sẽ lấy giá trị của 2 cột. 

![img](https://i.imgur.com/nRSxs6u.png)

Hơn nữa có filter và chặn `UNION`

![img](https://i.imgur.com/i9rfkva.png)

Bài này là Blind SQL injection nên kết quả trả về cũng không ra kết quả trả về rõ ràng. Nếu truy vấn là một khẳng định đúng thì kết quả trả về sẽ là `Welcome back!`

![img](https://i.imgur.com/64JYPxA.png)

Như vậy ta lần lượt tìm kiếm các thông tin cần thiết. 

1. Thông tin về table trong cơ sở dữ liệu chứa giá trị đăng nhập của các user => Bảng `users`

![img](https://i.imgur.com/64JYPxA.png)

2. Thông tin về các cột cần thiết => `username`, `password`

![img](https://i.imgur.com/64pplZ9.png)

3. Tìm length của password => 9

![img](https://imgur.com/JY5UZ2T)

4. Tìm từng kí tự có trong password => password = `e2azO93i`

![img](https://i.imgur.com/S9UlaaZ.png)