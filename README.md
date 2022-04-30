## **Описание**
API для проекта социальной платформы Yatube.

Можно создавать текстовые посты с возможностью прикрепления изображений. Посты могут входить в группы-сообщества. Пользователи могут подписываться друг на друга. Есть возможность отслеживать как все посты, так и посты избранных авторов. 

Есть возможность оставлять комментарии к каждому посту.

Запросы GET, POST, PUT, PATCH, DELETE производятся к моделям, описывающим посты, группы, комментарии, подписки.

Данные формата JSON.

## **Использованные технологии**
- Python 3.7.9
- Django 2.2.16
- Django REST Framework 3.12.4
- djangorestframework-simplejwt 4.7.2
- djoser 2.1.0 для управления JWT-токенами
- Pillow 8.3.1

## **Установка**
1. Клонировать репозиторий и перейти в него в командной строке:

    `https://github.com/Innis8/api_final_yatube.git`

    `cd api_final_yatube`

2. Cоздать и активировать виртуальное окружение:

    `python3 -m venv venv`
    
    `source venv/bin/activate`
    
    `python3 -m pip install --upgrade pip`


    в Windows:

    `python -m venv venv`
    
    `source venv/scripts/activate`
    
    `python -m pip install --upgrade pip`
    
3. Установить зависимости из файла requirements.txt:

    `pip install -r requirements.txt`
    
4. Выполнить миграции:
    
    `python3 manage.py makemigrations`
    
    `python3 manage.py migrate`

    в Windows:
    
    `python manage.py makemigrations`
    
    `python manage.py migrate`
    
5. Запустить проект:

    `python3 manage.py runserver`
    
    в Windows:
    
    `python manage.py runserver`
    
## **Примеры запросов и ответов**
- *GET:* `http://127.0.0.1:8000/api/v1/`
    
    ответ:
    ```
    {
        "groups": "http://127.0.0.1:8000/api/v1/groups/",
        "posts": "http://127.0.0.1:8000/api/v1/posts/",
        "follow": "http://127.0.0.1:8000/api/v1/follow/"
    }
    ```

- *GET:* `http://127.0.0.1:8000/api/v1/posts/`

    ответ:
    ```
    {
        "count": 1,
        "next": null,
        "previous": null,
        "results": [
            {
                "id": 1,
                "text": "Что мы узнали на CinemaCon-2022 в Лас-Вегасе",
                "pub_date": "2022-04-30T14:48:52.757020Z",
                "author": "admin",
                "group": 1,
                "image": null
            }
        ]
    }
    ```

- *GET:* `http://127.0.0.1:8000/api/v1/posts/1/`
    
    ответ:
    ```
    {
        "id": 1,
        "text": "Что мы узнали на CinemaCon-2022 в Лас-Вегасе",
        "pub_date": "2022-04-30T14:48:52.757020Z",
        "author": "admin",
        "group": 1,
        "image": null
    }
    ```

- *POST:* `http://127.0.0.1:8000/api/v1/posts/`
    ```
    {
        "text": "Тестовый пост 2"
    }
    ```
    
    ответ:
    ```
    {
        "id": 2,
        "text": "Тестовый пост 2",
        "pub_date": "2022-04-30T16:12:55.757759Z",
        "author": "admin",
        "group": null,
        "image": null
    }
    ```
    
- *PATCH:* `http://127.0.0.1:8000/api/v1/posts/2/`
     ```
    {
        "text": "Отредактированный Тестовый пост 2"
    }
    ```
    ответ:
    ```
    {
        "id": 2,
        "text": "Отредактированный Тестовый пост 2",
        "pub_date": "2022-04-30T16:12:55.757759Z",
        "author": "admin",
        "group": null,
        "image": null
    }
    ```
