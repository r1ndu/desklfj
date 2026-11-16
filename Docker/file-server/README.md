## Файловый обменник

Выполните все этапы работы с проектом по примеру с [Nginx](/content/Docker/ImageLibrary/Nginx.md)

> Никогда в разработке не используйте русские имена файлов и каталогов!

> Никогда в разработке не используйте пробелы и спец.символы в именах файлов и каталогов!

> Перед созданием проекта убедитесь, что порт 8084 не занят другим приложением!

> Создание проекта лучше начать с "чистого листа", предварительно остановив и удалив все другие контейнеры и образы!

1. Запустить **simple-http-server** для раздачи файлов

в **Git-Bash/Linux/WSL 2.0/Mac**
```shell
docker run -d \
  --name my-apache-server \
  -p 127.0.0.1:8084:80 \
  -v "$(pwd):/usr/local/apache2/htdocs/:ro" \
  httpd:alpine
```
![Скрин](/Docker/file-server/img/run.png)
2. [Откройте: http://localhost:8084](http://localhost:8084)
![Скрин](/Docker/file-server/img/files.png)
![Скрин](/Docker/file-server/img/file.png)
