# API YAMDB
Проект представляет собой API сервиса yatube.
Сервис предназначен для получения информации и обсуждения наиболее интересных произведений

## Стэк технологий:
- Python
- Django Rest Framework
- Postgres
- Docker

## Документация и возможности API:
К проекту подключен redoc. Для просмотра документации используйте эндпойнт redoc/
Использована аутентификация по JWT-токенам.
У неаутентифицированных пользователей доступ к API только на чтение. Исключение — эндпоинт /follow/.
Аутентифицированным пользователям разрешено изменение и удаление своего контента, в остальных случаях доступ предоставляется только на чтение.

## Квикстарт:
1) Склонируйте репозитрий на свой компьютер.
2) Создайте .env файл в директории infra/, в котором должны содержаться следующие переменные:
- DB_ENGINE=django.db.backends.postgresql
- DB_NAME= # название БД\ POSTGRES_USER= # ваше имя пользователя
- POSTGRES_PASSWORD= # пароль для доступа к БД
- DB_HOST=db
- DB_PORT=5432\
3) Из папки infra/ соберите образ при помощи docker-compose $ docker-compose up -d --build
4) Примените миграции $ docker-compose exec web python manage.py migrate
5) Соберите статику $ docker-compose exec web python manage.py collectstatic --no-input
6) Для доступа к админке не забудьте создать суперюзера $ docker-compose exec web python manage.py createsuperuser
