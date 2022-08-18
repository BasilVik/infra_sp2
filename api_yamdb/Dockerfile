# FROM python:3.7-slim

# RUN apt update && apt install -y gcc libpq-dev

# WORKDIR /app/api_yamdb

# COPY api_yamdb/requirements.txt /app

# RUN pip3 install -r /app/requirements.txt --no-cache-dir

# COPY ./ /app

# CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]

FROM python:3.7-slim

# Создать директорию вашего приложения.
RUN mkdir /api_yamdb

# Скопировать с локального компьютера файл зависимостей
# в директорию /app.
COPY requirements.txt /api_yamdb

# Выполнить установку зависимостей внутри контейнера.
RUN pip3 install -r /app/requirements.txt --no-cache-dir

# Скопировать содержимое директории /api_yamdb c локального компьютера
# в директорию /app.
COPY api_yamdb/ /api_yamdb

# Сделать директорию /app рабочей директорией. 
WORKDIR /api_yamdb

# Выполнить запуск сервера разработки при старте контейнера.
CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]