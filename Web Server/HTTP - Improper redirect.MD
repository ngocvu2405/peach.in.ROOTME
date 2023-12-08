## Link challenge: [HTTP - Improper redirect](https://www.root-me.org/en/Challenges/Web-Server/HTTP-Improper-redirect)

Với challenge ta thấy chưa gì đã thấy tham số `redirect` vậy là trang login này xuất hiện do ta đã bị redirect rồi.

Gợi ý của có đề cập: `Get access to index.` Có lẽ trang login được redirect từ trang index rồi này.

Thử gửi request sửa thành `index.php` sẽ thấy response trả về là 302 Found và thấy được source code bị lộ bao gồm cả flag.

![img](https://i.imgur.com/zt5raax.png)

Cá nhân mình thấy mình mong đợi nhiều hơn ở challenge này để chuyển 302 to 200 mà không có thấy.