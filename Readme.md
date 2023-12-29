<span style="font-size:2.2em;">**Задание 2**</span>

1.Сделайте в своем github пространстве fork репозитория https://github.com/netology-code/shvirtd-example-python/blob/main/README.md.

✔
-
![img.png](img.png)

2.Создайте файл с именем Dockerfile.python для сборки данного проекта. Используйте базовый образ python:3.9-slim. Протестируйте корректность сборки. Не забудьте dockerignore.

✔
-
![img_5.png](img_5.png)
![img_6.png](img_6.png)

3.(Необязательная часть, *) Изучите инструкцию в проекте и запустите web-приложение без использования docker в venv. (Mysql БД можно запустить в docker run).

✔
-

- поднял контейнер с MySQL
![img_7.png](img_7.png)
- запустил виртуальную среду venv
![img_8.png](img_8.png)
- Прописал порт в коде и объявил переменные для коннекта бд
![img_9.png](img_9.png)
![img_10.png](img_10.png)
- Запуск
![img_11.png](img_11.png)
4.(Необязательная часть, *) По образцу предоставленного python кода внесите в него исправление для управления названием используемой таблицы через ENV переменную.

✔
-
![img_14.png](img_14.png)
![img_13.png](img_13.png)


<span style="font-size:2.2em;">**Задание 2**</span>

![console.cloud.yandex.ru_folders_b1gcn2qnmrs7g9fq1f50_container-registry_registries_crpqjs9qp1emch06cj07_overview_pythonapp_image_crpehc7od1fu2q7ggcqr_scan-result_che1d8v72um9uhk7sas8_overview.png](..%2F..%2FDownloads%2Fconsole.cloud.yandex.ru_folders_b1gcn2qnmrs7g9fq1f50_container-registry_registries_crpqjs9qp1emch06cj07_overview_pythonapp_image_crpehc7od1fu2q7ggcqr_scan-result_che1d8v72um9uhk7sas8_overview.png)

<span style="font-size:2.2em;">**Задание 3**</span>

✔
-

1. Создайте файл compose.yaml. Опишите в нем следующие сервисы:
- web. Образ приложения должен ИЛИ собираться при запуске compose из файла Dockerfile.python ИЛИ скачиваться из yandex cloud container registry(из задание №2 со *). Контейнер должен работать в bridge-сети с названием backend и иметь фиксированный ipv4-адрес 172.20.0.5. Сервис должен всегда перезапускаться в случае ошибок. Передайте необходимые ENV-переменные для подключения к Mysql базе данных по сетевому имени сервиса web



- db. image=mysql:8. Контейнер должен работать в bridge-сети с названием backend и иметь фиксированный ipv4-адрес 172.20.0.10. Явно перезапуск сервиса в случае ошибок. Передайте необходимые ENV-переменные для создания: пароля root пользователя, создания базы данных, пользователя и пароля для web-приложения.Обязательно используйте .env file для назначения секретных ENV-переменных!

![img_16.png](img_16.png)
2. Запустите проект локально с помощью docker compose , добейтесь его стабильной работы.Протестируйте приложение с помощью команд curl -L http://127.0.0.1:8080 и curl -L http://127.0.0.1:8090.
![img_17.png](img_17.png)
3. Подключитесь к БД mysql с помощью команды docker exec <имя_контейнера> mysql -uroot -p<пароль root-пользователя> . Введите последовательно команды (не забываем в конце символ ; ): show databases; use <имя вашей базы данных(по-умолчанию example)>; show tables; SELECT * from requests LIMIT 10;.
![img_18.png](img_18.png)
4. Остановите проект. В качестве ответа приложите скриншот sql-запроса.
![img_19.png](img_19.png)