![push](https://github.com/ChthonicAnn/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)

# REST API для сервиса YaMDb

YaMDb — это база данных отзывов на фильмы, книги, музыку и другие произведения. Проект собирает пользовательские отзывы о произведениях. Произведения разделены на категории, например: «Книги», «Фильмы», «Музыка». Каждое произведение может быть отнесено к нескольким жанрам. Новые категории и жанры может создавать только администратор. Пользователи оставляют отзывы и ставят оценки произведениям по шкале от 1 до 10, на основе которых рассчитывается средняя оценка.

Особенности:

- Аутентификация через JWT-токены
- Поддержка методов GET, POST, PUT, PATCH, DELETE
- Данные предоставляются в формате JSON
- Создан в команде из трех человек с использованием Git в рамках курса от Яндекс.Практикума

## Технологический стек

- Django REST Framework (DRF)
- Simple JWT library
- django-filter library
- SQLite3 database
- git version control system

## Как начать работу

Инструкция для запуска проекта в Docker-контейнере.

### Предварительные требования

Для запуска контейнера потребуется установленный Docker:

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

### Использование

1) Запустите контейнеры с проектом:
```
docker-compose up 
```
2) Выполните миграции:
```
docker-compose exec web python manage.py migrate
```
3) Создайте суперпользователя:
```
docker-compose exec web python manage.py createsuperuser
```
4) Соберите статические файлы проекта:
```
docker-compose exec web python manage.py collectstatic --no-input
```
5) При необходимости загрузите тестовые данные:
```
docker-compose exec web python manage.py filldatabase
```

### Шаблон файла .env

```
DB_ENGINE=<...> # indicate that we are working with postgresql
DB_NAME=<...> # database name
POSTGRES_USER=<...> # login to connect to the database
POSTGRES_PASSWORD=<...> # password for connecting to the database (set your own)
DB_HOST=<...> # service (container) name
DB_PORT=<...> # port for connecting to the database
SECRET_KEY=<...> # key from settings.py
```

__________________________________
Ваш проект запущен по адресу: http://127.0.0.1:8000/
Полная документация доступна по адресу: http://127.0.0.1:8000/redoc/

## Авторы

* **Анастасия Ёрина** - [ChthonicAnn](https://github.com/ChthonicAnn/)
