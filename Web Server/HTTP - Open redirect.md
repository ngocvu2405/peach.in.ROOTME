## Link challenge: [HTTP - Open redirect](https://www.root-me.org/en/Challenges/Web-Server/HTTP-Open-redirect)

Mở challenge ta thấy có 3 button dẫn tới các trang web khác, thử chặn request khi nhấp vào link xem sao...

![img1](https://i.imgur.com/YiuapOU.png)

Ta thấy có 2 tham số đc truyền vào request này: url sẽ chuyển đấy và một tham số h.

Dùng tool check xem đấy là hàm hash nào, thấy:

![img2](https://i.imgur.com/RoQ28CN.png)

Vậy tham số h có thể là hash MD4 hoặc MD5. Tiếp tục decrypt đoạn hash xem là từ đâu:

![img3](https://i.imgur.com/odggpQv.png)

À vậy là chỉ cần hash MD5 website sẽ redirect tới là được nè. Test thử một trang web khác với kiểu hash này xem nào

![img4](https://i.imgur.com/xMBYPS4.png)

Forward thử ra flag liền nè:

![img5](https://i.imgur.com/3ETf785.png)








