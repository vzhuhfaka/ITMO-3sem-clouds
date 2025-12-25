**Отчет по облачной лабе 1 (Вариант 2)**<br>
**Выполнил Останин Андрей**

Ссылка на google drive с .csv файлом: https://drive.google.com/file/d/1H0DezJ32ekZ34Lw0wrpG-bAoP2qiQre7/view?usp=sharing

### Действия которые привели к результату:

Сначала импортировал исходные данные из .csv в .xlsx

Для AWS мы использовали данные из файла ```Mapping Rules AWS team 2.csv```, для Azure — из ```Azure lab team 2.csv```. Работа выполнялась так:

1. Анализ структуры данных — изучение предоставленных полей (Product Code, Usage Type, Meter Category и т.д.)

2. Разработка классификационной схемы на основе 5 уровней:
- IT Tower (основная категория)
- Service Family (подкатегория)
- Service Type (конкретный сервис)
- Service Sub Type (вариант сервиса)
- Service Usage Type (тип потребления)

3. Сопоставление сервисов с документацией провайдеров
  
4. Унификация терминологии для кросс-провайдерного сравнения

### Классифицированные сервисы и их назначение
### Сервисы AWS
## Вычислительные сервисы (Compute)

- Amazon EC2 — виртуальные серверы с разными типами инстансов (On-Demand, Dedicated Host, GPU). Аналог в российских облаках: ВМ в VK Cloud.

- AWS CodeBuild — CI/CD сервис для сборки и тестирования кода. Аналог: GitLab CI/CD в Selectel.

## Сервисы хранения (Storage)

- Amazon S3/Backup — объектное хранилище и сервис резервного копирования с разными классами хранения (Cold, Warm). Аналог: Yandex Object Storage.

- Amazon DynamoDB — NoSQL база данных с оплатой за пропускную способность (Read/Write Capacity Units). Аналог: Yandex Cloud.

## Сетевые сервисы (Networking)

- Elastic Load Balancer — распределение нагрузки между инстансами. Аналог: Load Balancer в Yandex Cloud.

- Elastic IP — статические публичные IP-адреса. Аналог: плавающие IP-адреса в российских облаках.

## Управляемые сервисы (Cloud Services)

- Amazon CloudWatch — мониторинг и алертинг. Аналог: Cloud Monitoring в Yandex Cloud.

-AWS Device Farm — тестирование приложений на реальных устройствах. Не нашел.

- AI сервисы (Translate, Transcribe, Comprehend) — готовые NLP-решения. Аналог: Yandex SpeechKit.

### Сервисы Azure
### Вычислительные сервисы (Compute)

- Azure Virtual Machines — виртуальные машины с разными ОС (Windows, RHEL) и лицензиями. Аналог: аналогичные ВМ в российских облаках.

- Azure HDInsight — управляемый Hadoop/Spark. Аналог: Data Proc в Yandex Cloud.

## Сервисы хранения (Storage)

- Azure Data Management/Backup — управление данными и резервное копирование с гео-репликацией. Аналог: VK Cloud Solutions Backup.

- Azure Data Lake Store — хранилище для big data аналитики. Аналог: Yandex Object Storage для аналитики.

## Сетевые сервисы (Networking)

- Azure Bastion — безопасный доступ к ВМ по RDP/SSH через браузер. Аналог: подобные решения есть в VK Cloud через VPN.

## Управляемые сервисы (Cloud Services)

- Azure API Management — шлюз для управления API. Аналог: API Gateway в Yandex Cloud.

- Azure Machine Learning — платформа для ML разработки. Аналог: Yandex DataSphere.

- Azure Data Factory — оркестрация ETL процессов. Аналог: Yandex Data Transfer.

- Azure Monitor — мониторинг и уведомления. Аналог: аналоги в российских облаках.

**Источники**
- [https://docs.aws.amazon.com/](https://learn.microsoft.com/ru-ru/azure/?product=popular)
