## Link challenge: [JWT - Introduction](https://www.root-me.org/en/Challenges/Web-Server/JWT-Introduction)

Thử đăng nhập với `guest`, thấy response trả về set cookie có variable jwt.

![Imgur](https://i.imgur.com/6AqBbu2.png)

Ta decode thử xem cấu trúc của jwt đó có gì

![Imgur](https://i.imgur.com/FIY1j5g.png)

Đọc ref ta thấy có thể attack bằng cách đổi biến "alg" từ `HS256` thành `none` và bỏ phần Signature nhưng vẫn giữ lại dấu chấm. Ta encode lại và đặt Cookie với biến jwt vừa encode rồi gửi lại request. Với bài này, ta đổi cả username của Payloads thành `admin`

![Imgur](https://i.imgur.com/3a6Ca6r.png)

DONE!