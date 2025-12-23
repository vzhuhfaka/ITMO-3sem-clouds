# Останин Андрей, лаба 1(nginx)
Отчет по первой лабе(nginx). 

Ну хочу начать с того, что у меня стоит винда, что значит, что работать с nginx будет не очень удобно( 
поэтому для начала ставлю убунту на виртуалку. Спустя несколько полностью намертво зависших виртуалок, каким-то чудом смог таки запустить линукс(я не понимаю почему оно работает(оно по идее не должно работать, но все работает значит не трогаем))

Далее создадим 2 проекта(просто html странички)<br><br>
<img width="901" height="630" alt="image" src="https://github.com/user-attachments/assets/c2e0462c-1451-400d-8e0d-694b07474108" />
<img width="611" height="190" alt="image" src="https://github.com/user-attachments/assets/36a92d99-3938-4635-97b2-917486231f04" /><br><br>
ну и вписал туда просто project1 и project2 текстом как контент. <br><br>

Теперь создадим директорию для alias<br><br>
<img width="897" height="565" alt="image" src="https://github.com/user-attachments/assets/43604559-7e66-4bfd-b092-bae30e45a891" /><br><br>
и файл index.html для теста<br><br>

Теперь создадим ssl сертификаты через openssl (благо ранее я уже делал подобное и примерно помню как делать + великий интернет)
для proj1<br><br>
<img width="816" height="540" alt="image" src="https://github.com/user-attachments/assets/f0964f21-0d7c-4ca0-a489-763f388bc851" /><br><br>
и для proj2 тоже. <br><br>

теперь напишем сами конфиги для двух проектов<br><br>
<img width="623" height="476" alt="image" src="https://github.com/user-attachments/assets/52eed58e-5208-4e4e-8da3-5c3f1b27c269" /><br><br>
где в первой части переадресовываем с порта 80 на 443, а во второй поключаем сам проект и сертификаты к нему, которые только сгенерили.
<br><br>
Время тестов!
Когда я перезапустил nginx, пошел в браузер тестить. У меня не находило страницы по адресам proj1.com и proj2.com я не понял сначала почему, но потом понял что для локальной сети надо внести  адреса в /etc/hosts<br><br>
<img width="830" height="148" alt="image" src="https://github.com/user-attachments/assets/fc78d3e4-35bb-4e56-89b8-9090ab6f3098" /><br><br>
После чего пошел тестить снова увидел что по адресу proj1.com браузер ругается на самоподписанный ssl(позже фиксану)<br><br>
<img width="1120" height="788" alt="image" src="https://github.com/user-attachments/assets/9ac35ca5-cdac-461c-abac-8aa2a4327182" /><br><br>
Но при продолжении страничка выходила нужная<br><br>
<img width="1030" height="530" alt="image" src="https://github.com/user-attachments/assets/e0016899-88b8-4f97-aa38-b79167f90449" /><br><br>
Когда я перешел на адрес proj2.com увидел это и че то ничего не понял. Оказывается этот адрес уже занят в интеренете и блокнут у меня(получается повезло что proj1.com свободен)<br><br>
<img width="1239" height="807" alt="image" src="https://github.com/user-attachments/assets/94039637-83e4-4476-87ed-8a07373ae08e" /><br><br>
Пришлось менять адрес для второго проекта на proj2.local и добавлять его снова в /etc/hosts.
После чего все заработало<br><br>
<img width="918" height="554" alt="image" src="https://github.com/user-attachments/assets/21ef3f42-bf68-4fde-be0b-6a8339f04087" /><br><br>

<br><br>
По поводу предупреждения о самоподписанном сертификате, я не знаю как это убрать(возможно только если кинуть в игнор)<br>
(Как же надоела эта приставка sudo для всего((( )<br>
На этом вроде как все) 
