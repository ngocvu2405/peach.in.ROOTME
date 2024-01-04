## Link challenge: [File upload - MIME type](https://www.root-me.org/en/Challenges/Web-Server/File-upload-MIME-type)

Như bài trước, ta tiếp tục dùng được source này để truy cập vào server thông qua upload file:

Với MIME Type mà đề bài đã gợi ý, sau đó đọc trong ref thì biết rằng có thể upload đc file thông qua sửa Content-Type thành text/plain hoặc image/gif,... trong các trường hợp khác nhau để upload được file
![img1](https://i.imgur.com/nDulCqf.png)

Sau khi upload được file, ta lại thêm command để tìm kiếm và cat file chứa flag
![img2](https://i.imgur.com/GChsWDV.png)