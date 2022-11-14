## api_yamdb
REST API для сервиса YaMDb — базы отзывов о фильмах, книгах и музыке. 
(Совместный проект студентов Яндекс.Практикума) ip проекта: 130.193.36.9
![example workflow](https://github.com/Evi1Russian/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)


## Описание
API для сервиса YaMDb дает возможность:

Получить список всех отзывов, создать новый отзыв, получить отзыв по id, частично обновить 
отзыв по id, удалить отзыв по id;

Получить список всех комментариев к отзыву по id, создать новый комментарий для отзыва, 
получить комментарий для отзыва по id, частично обновить комментарий к отзыву по id, 
удалить комментарий к отзыву по id;

JWT-токен Отправление confirmation_code на переданный email, получение JWT-токена в 
обмен на email и confirmation_code;

Пользователи (Получить список всех пользователей, создание пользователя, получить 
пользователя по username, изменить данные пользователя по username, удалить пользователя 
по username, получить данные своей учетной записи, изменить данные своей учетной записи;

Получить список всех категорий, создать категорию, удалить категорию;

Получить список всех жанров, создать жанр, удалить жанр;

Получить список всех объектов, создать произведение для отзывов, информация об объекте, 
обновить информацию об объекте, удалить произведение.

## Участники 
[Анна](https://github.com/AnnaBerk) - управление пользователями (Auth и Users): система регистрации и аутентификации, права доступа, работа с токеном, система подтверждения e-mail, поля.

[Олег](https://github.com/Evi1Russian) - категории (Categories), жанры (Genres) и произведения (Titles): модели, view и эндпойнты для них.

[Алексей](https://github.com/imvarlamov) - отзывы (Review) и комментарии (Comments): модели и view, эндпойнты, права доступа для запросов. Рейтинги произведений.


## [Полная документация API (redoc.yaml)](https://github.com/Evi1Russian/api_yamdb/blob/dev/api_yamdb/static/redoc.yaml)


## Установка
Клонировать репозиторий:
```bash
git@github.com:Evi1Russian/infra_sp2.git
```
Перейти в папку с проектом:
```bash
cd infra_sp2/
```
В папке infra создайте файл .env и запишите туда следующие переменные
```bash
DB_ENGINE=django.db.backends.postgresql
POSTGRES_USER=postgres
POSTGRES_PASSWORD=12345 # Придумайте свой
DB_HOST=db
DB_PORT=5432
SECRET_KEY=p&l%385148kslhtyn^##a1)ilz@4zqj=rq&agdol^##zgl9(vs
ADMIN_EMAIL=admin@mail.com
```
Установить контейнеры для проекта:
```bash
docker-compose up -d --build
```

Выполнить миграции на уровне проекта:
```bash
docker-compose exec web python manage.py migrate
```

Зарегистирировать суперпользователя Django:
```bash
docker-compose exec web python manage.py createsuperuser
```
адрес панели администратора
http://localhost/admin

## [Полная документация API (redoc.yaml)](https://github.com/Evi1Russian/api_yamdb/blob/dev/api_yamdb/static/redoc.yaml)
