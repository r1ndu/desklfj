## Python для запуска скриптов

Выполните все этапы работы с проектом по примеру с [Nginx](/content/Docker/ImageLibrary/Nginx.md)

> Никогда в разработке не используйте русские имена файлов и каталогов!

> Никогда в разработке не используйте пробелы и спец.символы в именах файлов и каталогов!

> Создание проекта лучше начать с "чистого листа", предварительно остановив и удалив все другие контейнеры и образы!

1. Создайте **Python** скрипт

в **Git-bash**
```shell
echo "print('Hello from Python in Docker')" > script.py
```

2. Запустите скрипт в контейнере с **Python**

в **Git-Bash**
```shell
docker run --rm -v "$(pwd)":/app python:alpine python /app/script.py
```
![Скрин](/Docker/Python/img/run.png)
3. Интерактивный **Python** (опционально)
```shell
docker run -it --rm python:alpine python
```
