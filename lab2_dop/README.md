# Останин Андрей, лаба 2*
Здравствуйте, это мой отчет по второй* лабе. Начну с того, что создал 2 dockerfile-compose в разных директориях: в badDC и goodDC:

## "Плохой" docker-compose
<img width="399" height="384" alt="image" src="https://github.com/user-attachments/assets/1f0c51da-7682-4590-8090-d0abf2b56b21" /><br><br>
bad-practice, которые присутствуют в этом файле:
- latest версии библиотек: плохо, потому что при обновлении библиотеки, наш код может полететь и перестать работать
- хранение паролей прямо в docker-compose.yml: это небезопасно, ведь пароль может случайно оказаться в репозитории
- явное задание container_name: могут возникать проблемы при масштабировании, да и причем docker-compose сам дает удобные названия к контейнерам
- данные в БД не сохраняются при перезапуске контейнера

И все работет<br>
<img width="1715" height="267" alt="image" src="https://github.com/user-attachments/assets/1b8a2431-6111-4378-930a-d49c80f7190e" />
<img width="1203" height="819" alt="image" src="https://github.com/user-attachments/assets/e5413f47-5de5-484b-a6f1-834634286434" />

## "Хороший" docker-compose
<img width="490" height="441" alt="image" src="https://github.com/user-attachments/assets/efc40008-babc-412a-a8dd-c65b03db4eb1" /><br>
Исправления:
- теперь стоят точные версии библиотек
- хранение паролей вынесено в отдельный .env файл
- убрано container_name
- добавлены volums для хранения данных в БД

## Изоляция контейнеровю
Для изоляции двух контейнеров в одном docker-compose нужно создать разные сети для этих контейнеров, так они будут запускаться вместе, но в разных сетях, а следовательно и изолированно друг от друга<br>
<img width="453" height="654" alt="image" src="https://github.com/user-attachments/assets/06d3662c-baf9-4371-aaa2-4d5c98329c66" /><br><br>

Вот проверка доступа из контейнера с nginx в контейнер postgres:<br>
<img width="671" height="142" alt="image" src="https://github.com/user-attachments/assets/5f49bebf-a74b-477f-a10c-1ab16e3f67a4" />


На этом все) 
