## Link challenge: [PHP - Comand Injection](https://www.root-me.org/en/Challenges/Web-Server/PHP-Command-injection)

Ở trang web này ta sẽ thấy một ô nhập IP, có vẻ như để ping tới địa chỉ IP mà người dùng nhập vào.

![img1](https://i.imgur.com/oT8hcCD.png)

Kết quả ping thử:

![img2](https://i.imgur.com/HvvCc80.png)

Thử tìm kiếm một chút xem phải làm thế nào để ping tới 1 địa chỉ IP bằng code PHP.

```
<?php
exec("ping -c $timeDelay $ipAddress");
?>
```

Nếu đúng là website được code như trên thì sẽ thực hiện lệnh ping của OS command. Đó là:

```
ping -c $timeDelay $ipAddress
```

Thấy rằng nếu như vậy tham số ipAddress chính là tham số mình nhập vào placeholder của website. Nếu không được duyệt cẩn thận, ta rõ ràng có thể thêm bất cứ câu lệnh bổ sung vào đằng sau bằng shell script.

Ta thử câu lệnh như này vào placeholder:

```
127.0.0.1; ls
```

Nhận thấy có một dòng kết quả bổ sung là file index.php xuất hiện ở cuối danh sách

![img3](https://i.imgur.com/JyU9Z65.png)

yeah! Đọc thử file này xem sao, vì thấy trong gợi ý của đề bài cũng đề cập tới flag nằm ở trong file này:

```
; cat index.php
```

Thấy có một ô placeholder mới được xuất hiện, cộng với đó là một đoạn code bị biến thành comment:

![img4](https://i.imgur.com/eZV0Q8q.png)

Đọc đoạn code bị biến thành comment ấy, ta thấy có một tham số 'flag'. Và tham số này được đọc từ file có tên là '.passwd'. Có vẻ file này cũng nằm gần file 'index.php' thôi, vì chẳng thấy phải thêm địa chỉ gì cả mà lấy lun file.

Ta `ls - la` :

![img5](https://i.imgur.com/MJ0xfqr.png)

A kia rồi, cat vội ra xem thui! Ra flag rùi nè

![img6](https://i.imgur.com/VRh7h3L.png)

