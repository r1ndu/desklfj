## MongoDB (NoSQL)

Выполните все этапы работы с проектом по примеру с [Nginx](/content/Docker/ImageLibrary/Nginx.md)

> Никогда в разработке не используйте русские имена файлов и каталогов!

> Никогда в разработке не используйте пробелы и спец.символы в именах файлов и каталогов!

> Создание проекта лучше начать с "чистого листа", предварительно остановив и удалив все другие контейнеры и образы!

1. Запуск **MongoDB**

в **Git-Bash/Linux/WSL 2.0/Mac**
```shell
docker run -d \
  --name my-mongo \
  -p 127.0.0.1:27017:27017 \
  mongo:latest
```
![Скрин](/Docker/MongoDB/img/run.png)

2. Подключиться через shell
```shell
docker exec -it my-mongo mongosh
```
![Скрин](/Docker/MongoDB/img/shell.png)

Повыполняйте какие-нибудь команды в этой БД для проверки и пришлите скрины

Посмотреть базы данных
```shell
show dbs
```
![Скрин](/Docker/MongoDB/img/databases.png)
Создать/переключиться на базу
```shell
use myapp
```
![Скрин](/Docker/MongoDB/img/use.png)
Создать коллекцию и вставить документ
```shell
db.users.insertOne({ name: "Иван", age: 30, city: "Москва" })
```
![Скрин](/Docker/MongoDB/img/insert.png)
Найти документы
```shell
db.users.find()
```
![Скрин](/Docker/MongoDB/img/find.png)
Найти с фильтром
```shell
db.users.find({ age: { $gt: 25 } })
```
![Скрин](/Docker/MongoDB/img/filter.png)
Обновить документ
```shell
db.users.updateOne({ name: "Иван" }, { $set: { age: 31 } })
```
![Скрин](/Docker/MongoDB/img/update.png)
Удалить документ
```shell
db.users.deleteOne({ name: "Иван" })
```
Посмотреть коллекции
```shell
show collections
```
Выйти
```shell
exit
```
