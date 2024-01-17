## Link challenge: [JWT - Weak secret](https://www.root-me.org/en/Challenges/Web-Server/JWT-Weak-secret)

Trong challenge ta sẽ lần lượt mò ra các subweb:
```
/hello
/token
/admin
```

Nhiệm vụ của chúng ta trong bài này là phải xâm nhập được vào /admin trong khi được authen bằng jwt value. Có một điều đặc biệt của bài này so với bài Introduction là bài này có secret key trong đó!

Với từng subweb trên ta có chỉ dẫn lần lượt là

![Imgur](https://i.imgur.com/bUWA6iq.png)
![Imgur](https://i.imgur.com/USSnZaQ.png)
![Imgur](https://i.imgur.com/vDoCrQO.png)

Khi vào subweb /admin thì chúng ta cần thêm 1 header `Authorization: Bearer ...`

Nhưng khi vào với token có sẵn thì bị chặn bởi ko đúng, thử sửa thành value `role: admin` thì mọi thứ cũng không tiến triển gì, bởi bài này còn có secret key nên không thể chỉ thay thế vậy được.

![Imgur](https://i.imgur.com/TWPi5l4.png)

Dùng jwt_tools để xem key là gì thông qua dictionary là `rockyou.txt` bằng command:

`python3 jwt_tool.py eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJyb2xlIjoiZ3Vlc3QifQ.4kBPNf7Y6BrtP-Y3A-vQXPY9jAh_d0E6L4IUjL65CvmEjgdTZyr2ag-TM-glH6EYKGgO3dBYbhblaPQsbeClcw -C -d /usr/share/wordlists/rockyou.txt
`

![Imgur](https://i.imgur.com/tHvyReD.png)

Từ đó ta kiếm được key là `lol`

Giờ chỉ cần tự thay thế vào gen lại jwt bằng tool gen jwt online `https://jwt.io/`. Thay thế giá trị mới của jwt vào request ta thu được falg của bài.

![Imgur](https://i.imgur.com/jcutkx4.png)