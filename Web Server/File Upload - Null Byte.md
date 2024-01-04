## Link challenge: [File Upload - Null Byte](https://www.root-me.org/en/Challenges/Web-Server/File-upload-Null-byte)

Vẫn tiếp tục khám phá trong phần upload file, ta vẫn sử dụng đoạn code trước đó. Vì yêu cầu là upload chỉ file ảnh, ta upload file có tên `test.php.png`

Tuy nhiên khi upload xong, file này không thể lên được do không đúng định dạng. Có lẽ filter đã đọc được tên file `.php`

![img1](https://i.imgur.com/udGfuLn.png)

Có vẻ không ổn, đề bài có gợi ý là NULL BYTE, trước đó thì mình mới chỉ biết tới Null Byte trong Directory Travesal có khả năng có thể áp dụng được.

![img2](https://i.imgur.com/LHkS9Uw.png)

Đọc trong đây thì ta có thể thấy mình có thể áp dụng xem thử xem đổi tên file để mất đi đoạn `.php` xem được không.

![img3](https://i.imgur.com/3wjRROT.png)

File đã được upload thành công, ta dễ dàng lấy được flag khi vào xem file

![img4](https://i.imgur.com/dHjavgS.png)