## Link challenge: [HTTP - Verb tampering](https://www.root-me.org/en/Challenges/Web-Server/HTTP-verb-tampering)

HTTP Verb Tampering của ứng dụng web đối với các phương thức HTTP khác nhau truy cập các đối tượng hệ thống. Đối với mọi đối tượng hệ thống được phát hiện trong quá trình thử nghiệm, người thử nghiệm nên cố gắng truy cập tất cả các đối tượng đó bằng mọi phương thức HTTP.

Đặc tả HTTP 1.1 đầy đủ xác định các phương thức yêu cầu HTTP hợp lệ sau:

- OPTIONS
- GET
- HEAD
- POST
- PUT
- DELETE
- TRACE
- CONNECT

Nếu được bật, WebDAV cho phép một số phương thức HTTP khác:

- PROPFIND
- PROPPATCH
- MKCOL
- COPY
- MOVE
- LOCK
- UNLOCK

Trong challenge, khi mở challenge sẽ yêu cầu popup đăng nhập:
![img1](https://i.imgur.com/9kN0guy.png)


Thấy rằng truy cập dùng phương thức GET. Bình thường các trang web thường dùng GET/POST là phổ biến, nên thử đổi một method request lạ xem sao. Ở đây mình dùng PUT
![img2](https://i.imgur.com/Wsr1ENI.png)


Response trả về có flag xuất hiện:
![img3](https://i.imgur.com/skrxFGT.png)
