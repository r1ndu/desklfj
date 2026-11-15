## Практическая работа на примере готового образа Nginx в Docker

> **Nginx** - это легкий и небольшой веб-сервер

> Никогда в разработке не используйте русские имена файлов и каталогов!

> Никогда в разработке не используйте пробелы и спец.символы в именах файлов и каталогов!

> Создание проекта лучше начать с "чистого листа", предварительно остановив и удалив все другие контейнеры и образы!

## Этапы

Получить версию установленного у вас Docker

```shell
docker version
```
![Скрин](/Docker/Nginx/img/version.png)

Найти нужный образ на **Docker Hub**

```shell
docker search nginx
```
![Скрин](/Docker/Nginx/img/search.png)

Получить, создать и запустить Nginx

```shell
docker run -d --name my-nginx -p 127.0.0.1:80:80 nginx
```
![Скрин](/Docker/Nginx/img/run.png)

Показать все контейнеры

```shell
docker ps -a
```
![Скрин](/Docker/Nginx/img/containers.png)

Показать загруженный на ваш компьютер образ

```shell
docker images nginx
```
![Скрин](/Docker/Nginx/img/images.png)

Показать работающий Nginx

```shell
curl http://localhost/
```
![Скрин](/Docker/Nginx/img/curl.png)

[Открыть http://localhost/ в браузере](http://localhost/)

![Скрин](/Docker/Nginx/img/web.png)

Показать подробности о контейнере

```shell
docker inspect --format "{{.State.Status}} {{.Config.Image}}" my-nginx
```
![Скрин](/Docker/Nginx/img/inspect.png)

Запустить мониторинг контейнеров

```shell
docker stats --no-stream my-nginx
```
![Скрин](/Docker/Nginx/img/stats.png)

Получить лог контейнера

```shell
docker logs --tail 3 my-nginx
```
![Скрин](/Docker/Nginx/img/logs.png)

Остановить контейнер

```shell
docker stop my-nginx
```
![Скрин](/Docker/Nginx/img/stop.png)

Снова запустить контейнер

```shell
docker start my-nginx
```
![Скрин](/Docker/Nginx/img/start.png)

Перезапустить контейнер

```shell
docker restart my-nginx
```
![Скрин](/Docker/Nginx/img/restart.png)

Зайти в контейнер

```shell
docker exec -it my-nginx /bin/bash
```
![Скрин](/Docker/Nginx/img/shell.png)

Получить информацию об ОС контейнера

```shell
uname -a
```
![Скрин](/Docker/Nginx/img/uname.png)

Получить больше информации об ОС контейнера

```shell
cat /etc/os-release
```
![Скрин](/Docker/Nginx/img/os.png)

Выйти из контейнера

```shell
exit
```

Отредактировать текст страницы приветствия **Nginx**

```shell
docker cp /tmp/imfua-nginx-index.html my-nginx:/usr/share/nginx/html/index.html
```
![Скрин](/Docker/Nginx/img/edit.png)

[Проверить изменения на открытой странице](http://localhost/)

![Скрин](/Docker/Nginx/img/web-edited.png)
