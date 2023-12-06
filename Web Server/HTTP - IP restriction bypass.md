## Link challenge: [HTTP - IP restriction bypass](https://www.root-me.org/en/Challenges/Web-Server/HTTP-IP-restriction-bypass)

Mở challenge ta thấy có một trang yêu cầu đăng nhập do không ở chung mạng nội bộ

![img1](https://i.imgur.com/zY7696h.png)

Vậy có nghĩa là nếu mình nằm trong LAN bằng một cách nào đó thì không cần phải đăng nhập gì sất. 

Trong reference rfc1918 ta thấy mạng nội bộ được sử dụng 3 dải IP:
```
     10.0.0.0        -   10.255.255.255  (10/8 prefix)
     172.16.0.0      -   172.31.255.255  (172.16/12 prefix)
     192.168.0.0     -   192.168.255.255 (192.168/16 prefix)
```
Tìm hiẻu một chút ta biết được có 1 header của HTTP là `X-Forwarded-For` có thể giúp xác định địa chỉ IP của máy kháchkết nối tới server bởi proxy

`The X-Forwarded-For (XFF) HTTP header field is a common method for identifying the originating IP address of a client connecting to a web server through an HTTP proxy or load balancer.`

Áp dụng header này vào ta có thể mặc nhiên sử dụng 1 trong số những IP trong dải private, từ đó server sẽ bị hiểu là mình đã nằm trong mạng nội bộ.
Mình lựa tạm cái IP: 10.24.1.1 :v 
![img2](https://i.imgur.com/PJgJPPH.png)

Và mình đã vào được cũng như lấy được flag nè:

![img3](https://i.imgur.com/1dpkzrl.png)
