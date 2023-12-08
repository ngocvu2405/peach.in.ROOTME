## Link challenge: [Backup File](https://www.root-me.org/en/Challenges/Web-Server/Backup-file)

Khi mở challenge ta thấy có một trang yêu cầu đăng nhập:

![img1](https://i.imgur.com/kehNwmC.png)

Đọc đề bài tên là backup, mình đọc chút về backup file vulnerable thì thấy rằng có thể những file .bak, .old có khả năng vẫn đang được lưu lại ở đâu đó trên website.

Vì vậy, mình scan web xem có file nào khả nghi không thì thấy trong đó có 2 trang access status 200:
```
[22:13:20] 200 -  531B  - /web-serveur/ch11/index.php                       
[22:13:21] 200 -  843B  - /web-serveur/ch11/index.php~   
```

Cái đầu tiên là web ban đầu rùi... vào thử link thứ 2 thì thấy có 1 file hiển thị download về :v backup file đây rồi nè! Mở file thì lấy đc username & password có thể sử dụng được và là flag luôn.

![img2](https://i.imgur.com/yVndxOH.png)

![img3](https://i.imgur.com/SkHupKS.png)

