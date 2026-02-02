# Project API (Flask) — подбор мест для прогулки по Москве

Веб-приложение на Flask: пользователь регистрируется/входит, отвечает на вопросы, после чего получает подборку мест и отображение на карте. Есть загрузка картинки пользователем.

## Функциональность
- Регистрация и авторизация пользователей (Flask-Login)
- Опрос (3 вопроса), сохранение результатов в базе данных (SQLite)
- Страница `/map` — карта с точками в зависимости от ответов
- CRUD для ответов (добавить / редактировать / удалить)
- Загрузка изображения (`/file_upload`) и сохранение в `static/img/`

## Технологии
- Python 3
- Flask, Jinja2, Bootstrap (шаблоны)
- Flask-Login, Flask-WTF
- SQLAlchemy + SQLite
- Pillow 

## Структура проекта
- `server.py` — точка входа, маршруты Flask
- `data/` — модели и подключение к БД
- `forms/` — формы (регистрация, логин, вопросы)
- `templates/` — HTML шаблоны
- `static/` — CSS/картинки и загруженные изображения
- `requirements.txt` — зависимости проекта

## Установка и запуск (Ubuntu)

```bash
# 1) перейти в папку проекта (где лежит server.py)
cd ~/Desktop/projects/project_api/project_api

# 2) создать виртуальное окружение и активировать его
python3 -m venv .venv
source .venv/bin/activate

# 3) установить зависимости
python -m pip install -U pip
python -m pip install -r requirements.txt

# 4) подготовить папки
mkdir -p static/img
mkdir -p db

# 5) база данных
# В проекте используется путь db/blogs.db.
test -f blogs.db && mv blogs.db db/blogs.db

# 6) запуск
python server.py

# 7) открыть http://127.0.0.1:5000/
