## **��������**
API ��� ������� ���������� ��������� Yatube.

����� ��������� ��������� ����� � ������������ ������������ �����������. ����� ����� ������� � ������-����������. ������������ ����� ������������� ���� �� �����. ���� ����������� ����������� ��� ��� �����, ��� � ����� ��������� �������. 

���� ����������� ��������� ����������� � ������� �����.

������� GET, POST, PUT, PATCH, DELETE ������������ � �������, ����������� �����, ������, �����������, ��������.

������ ������� JSON.

## **�������������� ����������**
- Python 3.7.9
- Django 2.2.16
- Django REST Framework 3.12.4
- djangorestframework-simplejwt 4.7.2
- djoser 2.1.0 ��� ���������� JWT-��������
- Pillow 8.3.1

## **���������**
1. ����������� ����������� � ������� � ���� � ��������� ������:

    `https://github.com/Innis8/api_final_yatube.git`

    `cd api_final_yatube`

2. C������ � ������������ ����������� ���������:

    `python3 -m venv venv`
    
    `source venv/bin/activate`
    
    `python3 -m pip install --upgrade pip`


    � Windows:

    `python -m venv venv`
    
    `source venv/scripts/activate`
    
    `python -m pip install --upgrade pip`
    
3. ���������� ����������� �� ����� requirements.txt:

    `pip install -r requirements.txt`
    
4. ��������� ��������:
    
    `python3 manage.py makemigrations`
    
    `python3 manage.py migrate`

    � Windows:
    
    `python manage.py makemigrations`
    
    `python manage.py migrate`
    
5. ��������� ������:

    `python3 manage.py runserver`
    
    � Windows:
    
    `python manage.py runserver`
    
## **������� �������� � �������**
- *GET:* `http://127.0.0.1:8000/api/v1/`
    
    �����:
    ```
    {
        "groups": "http://127.0.0.1:8000/api/v1/groups/",
        "posts": "http://127.0.0.1:8000/api/v1/posts/",
        "follow": "http://127.0.0.1:8000/api/v1/follow/"
    }
    ```

- *GET:* `http://127.0.0.1:8000/api/v1/posts/`

    �����:
    ```
    {
        "count": 1,
        "next": null,
        "previous": null,
        "results": [
            {
                "id": 1,
                "text": "��� �� ������ �� CinemaCon-2022 � ���-������",
                "pub_date": "2022-04-30T14:48:52.757020Z",
                "author": "admin",
                "group": 1,
                "image": null
            }
        ]
    }
    ```

- *GET:* `http://127.0.0.1:8000/api/v1/posts/1/`
    
    �����:
    ```
    {
        "id": 1,
        "text": "��� �� ������ �� CinemaCon-2022 � ���-������",
        "pub_date": "2022-04-30T14:48:52.757020Z",
        "author": "admin",
        "group": 1,
        "image": null
    }
    ```

- *POST:* `http://127.0.0.1:8000/api/v1/posts/`
    ```
    {
        "text": "�������� ���� 2"
    }
    ```
    
    �����:
    ```
    {
        "id": 2,
        "text": "�������� ���� 2",
        "pub_date": "2022-04-30T16:12:55.757759Z",
        "author": "admin",
        "group": null,
        "image": null
    }
    ```
    
- *PATCH:* `http://127.0.0.1:8000/api/v1/posts/2/`
     ```
    {
        "text": "����������������� �������� ���� 2"
    }
    ```
    �����:
    ```
    {
        "id": 2,
        "text": "����������������� �������� ���� 2",
        "pub_date": "2022-04-30T16:12:55.757759Z",
        "author": "admin",
        "group": null,
        "image": null
    }
    ```
