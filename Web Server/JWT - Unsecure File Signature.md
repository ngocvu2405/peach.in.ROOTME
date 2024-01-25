## Link challenge: [JWT - Unsecure File Signature](https://www.root-me.org/en/Challenges/Web-Server/JWT-Unsecure-File-Signature)]

Challenge này khi đọc gợi ý có vẻ sẽ liên quan tới biến  kid của jwt. 

Có một challenge tương tự ở portswigger về lỗ hổng này, có thể gần như thực hiện tương tự. [HERE](https://portswigger.net/web-security/jwt/lab-jwt-authentication-bypass-via-kid-header-path-traversal)

Đọc doc trên portswigger có thể dễ dàng áp dụng cho challenge này như sau.

Đầu tiên vẫn là scan web, ta thấy subweb đáng nghi là `/admin`. Khi thử zo, ta nhận được kết quả ko thể Authen:

![Imgur](https://i.imgur.com/jXhbLhW.png)

Ta thấy có một biến jwt ở Header Cookie gán giá trị cho session. Thử dịch xem có gì ở đây, ta thấy biến `kid` và một số thông tin liên quan.

![Imgur](https://i.imgur.com/q1zN95g.png)

Tham khảo về lỗ hổng này, ta có thể cho tham số `kid` lấy giá trị từ một file null mà theo gợi ý bên portswigger là `../../../../../../../dev/null`.  Vẫn thay đổi role `guest` thành `admin`.

![Imgur](https://i.imgur.com/Uit2JDb.png)

Oh! có vẻ đã bị filter khi cd file của biến kid, ta by pass thành `....//../....//....//....//....//....//dev//null`

![Imgur](https://i.imgur.com/rQsKW39.png)

Nhưng còn một vấn đề ở secret key, với secret key mình trỏ `kid` tới file null nên sửa key thành null. Nhưng do key chỉ nhận dạng text, nên ta sẽ sửa dụng kí tự null trong base64 là `==AA` để bypass biến này.

![Imgur](https://i.imgur.com/isVQY2G.png)