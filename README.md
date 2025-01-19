### <br>➜ https://dragunkitty.zapto.org/</br>

## Описание

Киттиграм - это платформа, где вы можете делиться фотографиями своих любимых котиков, а также находить милых пушистиков от других пользователей.

## Функционал

Вот что было сделано в ходе работы над проектом:
- создан собственный API-сервис на базе проекта Django;
- подключено SPA к бэкенду на Django через API;
- созданы образы и запущены контейнеры Docker;
- создано, развёрнуто и запущено на сервере мультиконтейнерное приложение;
- закреплены на практике основы DevOps, включая CI/CD.


## Инструкции по запуску проекта:
1. **Клонировать репозиторий**:
   ```bash
   git clone git@github.com:EmilDragunov/kittygram.git
   ```

2. **Перейти в директорию проекта**:
   ```bash
   cd foodgram/backend/
   ```

3. **Создать и активировать виртуальное окружение** (для Windows):
   ```bash
   python -m venv venv
   source venv/Scripts/activate
   ```

4. **Установить зависимости**:
   ```bash
   pip install -r requirements.txt
   ```
   
5. **Создать файл `.env`** в корне проекта с настройками

6. **Запустить проект с помощью Docker**:
   ```bash
   docker compose -f docker-compose.production.yml up -d
   ```

7. **Выполнить миграции и собрать статику**:
   ```bash
   docker compose -f docker-compose.production.yml exec backend python manage.py migrate
   docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic --no-input
   ```

8. **Создать суперпользователя**:
   ```bash
   docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser
   ```

8. **Наполнить базу данных предустановленными данными**:
   ```bash
   docker compose -f infra/docker-compose.production.yml exec backend python manage.py loaddata data/fixtures.json
   ```
