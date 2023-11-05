# Kittygram
Kittygram - блог для размещение фотографий котиков.
Описание проекта:
Проект Kittygram даёт возможность пользователям поделиться и похвастаться фотографиями своих любимымих котиков. Зарегистрированные пользователи могут создавать, просматривать, редактировать и удалять свои записи.

## Технологии
- Docker
- Git
- Nginx
- Gunicorn
- Python
- Django
- Django REST framework

## Секреты .env

```
SECRET_KEY='SECRET_KEY'
DEBUG=False
ALLOWED_HOSTS='ваш домен'
POSTGRES_USER=[имя_пользователя_базы]
POSTGRES_PASSWORD=[пароль_к_базе]
POSTGRES_DB= [имя_базы_данных]
DB_PORT=[порт_соединения_к_базе]
DB_HOST=[db]

```


### Запуск из образа Docker Hub
Для запуска необходимо скачать в папку проекта файл docker-compose.production.yml и запустить его:
```
sudo docker compose -f docker-compose.production.yml up
```
Произойдет скачивание образов, создание и включение контейнеров, создание томов и сети.

### Запуск проекта из исходников GitHub
Клонируем к себе репозиторий:
```
git clone git@github.com:Fedor-new-Hope/kittygram_final.git
```
Запускаем:
```
sudo docker compose -f docker-compose.yml up
```

### Миграции и сбор статики
```
sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py migrate

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py collectstatic

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend cp -r /app/collected_static/. /static/static/
```

Проект будет доступен локально по адресу [http://localhost:9000/](http://localhost:9000/)


Автор
Кулабухов Федор - GitHub