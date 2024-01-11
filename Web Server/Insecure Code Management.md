## Link challenge:[Insecure code management](https://www.root-me.org/en/Challenges/Web-Server/Insecure-Code-Management)

Đầu tiên, scan web sẽ thấy đc link git.

![img1](https://i.imgur.com/Lg7FzOj.png)

Tải .git về với câu lệnh:
`wget --recursive http://challenge01.root-me.org/web-serveur/ch61/.git/`

Sau khi tải, cd vào .git để sử dụng các lệnh git cần thiết: `cd (thư mục lưu)/challenge01.root-me.org/web-serveur/ch61/.git/`

Check log: `git log` ta thấy có một commit khả nghi, chắc là password cần tìm kiếm

![img2](https://i.imgur.com/Ecyprq6.png)

Show: `git show` đọc nội dung thì thấy luôn được password:

![img3](https://i.imgur.com/U3LZCWv.png)