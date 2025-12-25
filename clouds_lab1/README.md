**Отчет по облачной лабе 1 (Вариант 2)**<br>
**Выполнил Останин Андрей**

Ссылка на google drive с .csv файлом: https://drive.google.com/file/d/1n0id51ykyfj6n332ehDyMfqkmV_-PtkE/view?usp=sharing

Действия которые привели к результату:
Сначала импортировал исходные данные из .csv в .xlsx

Далее сопоставил по иерархии: 

Для каждой записи определены 5 уровней классификации:

- IT Tower (основная категория: Compute, Database, Storage, Networking и т.д.)
- Service Family (подкатегория внутри IT Tower)
- Service Type (конкретный сервис AWS)
- Service Sub Type (вариант использования сервиса)
- Service Usage Type (детальный тип потребления)

Ключевые решения при сопоставлении:
- Значения для IT Tower и Service Family взяты из образца Mapping Rules AWS Example.csv
- Строки с Tax% выделены в отдельный подтип "Additional Costs"
- Разные Usage Types одного Product Code получили разные Service Sub Types
- CloudWatch сохранён с Product Code = AmazonEC2 как в исходных данных

Пример иерархии:<br>
IT Tower: Compute<br>
Service Family: Compute<br>
Service Type: Amazon EC2<br>
Service Sub Type: Dedicated Host<br>
Service Usage Type: Dedicated Host Usage

**Источники**
- https://docs.aws.amazon.com/

