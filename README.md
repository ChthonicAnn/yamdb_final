![push](https://github.com/ChthonicAnn/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)

# Yamdb_final
### test

REST API for YaMDb service YaMDb is a database of reviews about films, books, music and other works. The YaMDb project collects user feedback on works. Works are divided into categories, for example: "Books", "Films", "Music". A work can be assigned to several genres. New categories and genres can only be created by the administrator. Readers leave reviews and ratings for works in the range from 1 to 10. Based on these data, an average rating is calculated.

Authentication by JWT token Supports GET, POST, PUT, PATCH, DELETE methods Provides data in JSON format Created in a team of three people using Git as part of the Yandex.Practice training course.

## Technology stack

- Django REST Framework (DRF)
- Simple JWT library
- django-filter library
- SQLite3 database
- git version control system

## Getting Started

These instructions will cover usage information and for the docker container 

### Prerequisities

In order to run this container you'll need docker installed.

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

### Usage

1) Expand containers with the project:
```
docker-compose up 
```
2) Run the migrations:
```
docker-compose exec web python manage.py migrate
```
3) Create a superuser:
```
docker-compose exec web python manage.py createsuperuser
```
4) Collect all "statics" of the project
```
docker-compose exec web python manage.py collectstatic --no-input
```
5) If necessary, you can upload test data:
```
docker-compose exec web python manage.py filldatabase
```

### env file template

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
Your project started at http://127.0.0.1:8000/
Full documentation available at http://127.0.0.1:8000/redoc/

## Authors

* **Anastasyya Yorina** - *Initial work* - [ChthonicAnn](https://github.com/ChthonicAnn)

