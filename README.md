![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white) ![djangorestframework](https://img.shields.io/badge/djangorestframework-brightgreen%20.svg?style=for-the-badge&logo=django&logoColor=white) ![Postman](https://img.shields.io/badge/postman-white.svg?style=for-the-badge&logo=postman&logoColor=#d95030)

## Учебный проект - Яндекс.Практика - API для Yatube


Была написана программа под чутким руководством учебного центра
"Яндекс Практикум". Данный проект представляет некую социальную
сеть в которой можно публиковать посты, размещать к ним картинки,
создавать группы, подписываться на авторов, оставлять комментарии.
Связь с проектом осуществляется по API, что дает возможность его
использовать разными сторонними программами на разных устройствах.

## Функционал
#### Не авторизованный пользователь может:

- Просматривать статьи;
- Просматривать информацию о группах;
- Просматривать комментарии.

#### Авторизованный пользователь может:

- Получить JWT-токена
- Просматривать статьи, публиковать, удалять и редактировать свои статьи;
- Просматривать информацию о группах;
- Подписываться на автора статей, и удалять подписку;
- Комментирование, просмотр, удаление и обновление комментариев.

## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:
```python
git clone git@github.com:Maksim1301/api_final_yatube.git
```
```python
cd api_final_yatube
```
Cоздать и активировать виртуальное окружение:
```python
python -m venv venv
```
* Если у вас Linux/macOS
    ```python
    source env/bin/activate
    ```
* Если у вас windows
    ```python
    source env/scripts/activate
    ```
Установить зависимости из файла requirements.txt:
```python
python -m pip install --upgrade pip
```
```python
pip install -r requirements.txt
```
Выполнить миграции:
```python
python manage.py migrate
```
Запустить проект:
```python
python manage.py runserver
```
Перейти:
```python
http://127.0.0.1:8000/
```
## Примеры запросов

Получаем JWT-токена
Отправить POST-запрос на адрес `api/v1/jwt/create/`
##### Payload
```python
{
    "username": - "имя пользователя",
    "password": - "пароль пользователя"
}
```
##### Response sample (status code = 200)
```python
{
    "refresh": "string",
    "access": "string"
}
```
Получение публикаций
Отправить POST-запрос на адрес `api/v1/posts/`
##### Response sample (status code = 200)
```python
{
    "count": 123,
    "next": "http://api.example.org/accounts/?offset=400&limit=100",
    "previous": "http://api.example.org/accounts/?offset=200&limit=100",
    "results": [
        {}
    ]
}
```

#### Более подробное описание API можно получить по адресу:

http://localhost:8000/redoc/