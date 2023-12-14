## Link challenge: [CLRF](https://www.root-me.org/en/Challenges/Web-Server/CRLF)

CL và RF căn bản là câu lệnh xuống dòng '\n' và '\r'. 

Nhiệm vụ của chúng ta là ghi log giả. Ta thấy mỗi lần connect lỗi/không là log sẽ ghi xuống dưới bằng 1 dòng. Theo nhiệm vụ mà chúng ta biết là vận dụng lỗ hổng của lệnh CLRF tức là có thể xuống dòng đột ngột.

Có %0D %0A là hai lệnh xuống dòng mình sẽ áp dụng

Thử với:
    Username: admin%20authenticated.%0Agues
    Password: admin

Như vậy sẽ in ra `admin authenticated.` sau đó xuống dòng và là log failed.

![img](https://i.imgur.com/P5WpsUk.png)