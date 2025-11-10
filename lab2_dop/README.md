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
<img width="490" height="441" alt="image" src="https://github.com/user-attachments/assets/efc40008-babc-412a-a8dd-c65b03db4eb1" />
Исправления:
- теперь стоят точные версии библиотек
- хранение паролей вынесено в отдельный .env файл
- убрано container_name
- добавлены volums для хранения данных в БД

## Изоляция контейнеровю


На этом все) 
