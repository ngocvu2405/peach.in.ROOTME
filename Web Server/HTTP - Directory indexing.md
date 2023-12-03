## Link challenge: [HTTP-Directory-indexing](https://www.root-me.org/en/Challenges/Web-Server/HTTP-Directory-indexing)

Khi mở cheallenge, không có bất kì nội dung gì trong trang web.

Đọc hint ở đề bài, ta thấy gợi ý mở source view (Ctrl+U)
![hdi1](https://imgur.com/9yqXfNz)

Thử nhấn Ctrl+U ta thấy source có comment:
![hdi2](https://imgur.com/vUEkySg)

Thử vào branch được tiết lộ ở include, ta thấy có vẻ đã đi sai hướng rồi :(
![hdi3](https://imgur.com/lFice5m)

Shh... Không sao cả, xem lại đề chút xem nào... Đề bài kêu mình là Directory... thử scan web xem có ra gì hem nào?
Ta dùng dirsearch kiếm thử, thấy có 4 mục status 200:
'''
[23:51:53] 200 -   12KB - /web-serveur/ch4/admin/                           
[23:51:53] 200 -   12KB - /web-serveur/ch4/admin/?/login
[23:51:54] 200 -   12KB - /web-serveur/ch4/admin/backup/                                  
[23:52:46] 200 -  252B  - /web-serveur/ch4/index.html  --> cái này mới vào là thấy rùi nè
'''

Thử ngay trang 200 đầut iên ta đã thấy rằng:
![hdi4](https://imgur.com/yrJQ3KB)
Chà chà, bắt được vàng rồi đây, xem thử dễ dàng tìm thấy FLAG được giấu ở dir: /web-serveur/ch4/admin/backup/admin.txt
'''
Password / Mot de passe : LINUX
'''
