## Link challenge: [JWT - Revoked token](https://www.root-me.org/en/Challenges/Web-Server/JWT-Revoked-token)

Đối với challenge này có vấn đề ở access token thông qua jwt bị chặn. Mình có source code để đọc lấy manh mối để trả lời cho từng vấn đề khi kiếm flag của bài này.

Đầu tiên thử với `/admin` thì response trả về là chưa có tham số Header để authen

![Imgur](https://i.imgur.com/QpyvOdS.png)

Truy cập thử với trang login, ta thấy họ yêu cầu cần thêm tham số đăng nhập và cũng cung cấp luôn tài khoản admin. Gửi truy cập với tham số được cung cấp (cần thay đổi cả Content-Type thành json/application) ta sẽ nhận được tham số jwt cần thiết để vào trang admin.

![Imgur](https://i.imgur.com/I6iNfKQ.png)

Vào trang admin và add thêm tham số authen jwT. Nhưng bị revoke... Đọc đoạn code được cung cấp ta thấy một đoạn code đã add jwt value vào blacklist ngay khi nó được tạo ra.

![Imgur](https://i.imgur.com/gm8y5iC.png)

Để bypass, ta add một kí tự nữa để vẫn giữ nguyên ý nghĩa của tham số jwt. Biết rằng jwt được encode bằng base64 nên ta thêm `==` ở cuối để không thay đổi ý nghĩa và lấy được flag.

![Imgur](https://i.imgur.com/BfEZMDY.png)