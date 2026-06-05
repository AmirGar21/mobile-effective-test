## Запуск


# Клонировать репозиторий 

`git clone git@gitlab.com:amirgaripi2001/mobile-effective-test.git`

# Из корневой директории проекта выполнить:


`docker compose up --build -d`

После успешного запуска будут подняты два контейнера:

`effective-mobile-backend`
`effective-mobile-nginx`
Проверка результата

Отправить HTTP-запрос:

`curl http://localhost`

Для проверки состояния контейнеров:

`docker compose ps`

Остановка проекта:

`docker compose down`

# Как работает схема

1. Пользователь отправляет HTTP-запрос на порт 80 контейнера Nginx.
2. Nginx выступает в роли reverse proxy и принимает запрос.
3. Nginx перенаправляет запрос на backend-сервис по внутренней Docker-сети (backend:8080).
4. Python-приложение обрабатывает запрос и возвращает ответ:
`Hello from Effective Mobile!`
5. Nginx получает ответ от backend и возвращает его пользователю.

## При этом backend-сервис не публикует свой порт наружу и доступен только из внутренней Docker-сети.