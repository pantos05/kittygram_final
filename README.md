# Kittygram - социальная сеть для размещение фотографий домашних животных.

## Описание проекта
Проект, где пользователи могут регистрироваться, загружать фотографии кошек с описанием их достижений, а также любоваться на других котов. (Но я загружаю собак)

## Технологии
•	Django==3.2.3
•	djangorestframework==3.12.4
•	djoser==2.1.0
•	gunicorn==20.1.0


## Автор
[@pantos05](https://github.com/pantos05)

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/pantos05/kittygram_final.git 
```

Перейти в корневую директорию
```
cd kittygram_final
```

Создать файл .evn для хранения ключей:

```
DEBUG=False
POSTGRES_USER='User БД'
POSTGRES_PASSWORD='Пароль от БД'
POSTGRES_DB='eg: Название БД'
DB_HOST='eg: db'
DB_PORT='Указать порт'
SECRET_KEY='Указать секретный ключ'
ALLOWED_HOSTS='eg: 127.0.0.1,localhost'
```

Запустить docker-compose.production:

```
docker compose -f docker-compose.production.yml up
```

Выполнить миграции, сбор статики:

```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/

```

Создать суперпользователя, ввести почту, логин, пароль:

```
docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser
```