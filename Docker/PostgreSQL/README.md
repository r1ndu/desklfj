## PostgreSQL

Выполните все этапы работы с проектом по примеру с [Nginx](/content/Docker/ImageLibrary/Nginx.md)

> Никогда в разработке не используйте русские имена файлов и каталогов!

> Никогда в разработке не используйте пробелы и спец.символы в именах файлов и каталогов!

> Создание проекта лучше начать с "чистого листа", предварительно остановив и удалив все другие контейнеры и образы!

Запуск **PostgreSQL** с паролем

в **Git-Bash/Linux/WSL 2.0/Mac**
```shell
docker run -d \
  --name my-postgres \
  -p 127.0.0.1:5432:5432 \
  -e POSTGRES_PASSWORD=mysecretpassword \
  postgres:alpine
```
![Скрин](/Docker/PostgreSQL/img/run.png)

Подключиться через `psql`
```shell
docker exec -it my-postgres psql -U postgres
```

- Выполнить несколько демонстрационных команд, например:

Получить список баз данных:
```sql
\l
```
![Скрин](/Docker/PostgreSQL/img/list.png)
Получить версию:
```sql
SELECT version();
```
![Скрин](/Docker/PostgreSQL/img/version.png)
выйти из БД
```sql
exit
```
