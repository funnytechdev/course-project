# Course project

Учебный проект: база данных PostgreSQL 16.4 в Docker Compose.
Используются только синтетические данные курса.

## Что нужно установить
- Git
- Docker Desktop (с Docker Compose)

## Запуск
1. Скопировать настройки: `cp .env.example .env`
2. Запустить базу: `docker compose up -d --wait`

## Проверка
- `docker compose ps --services` — сервис `db`
- `docker compose images` — образ `postgres:16.4`
- `docker volume ls` — том `postgres_data`
- `docker compose ps` — состояние `healthy`
- `docker compose port db 5432` — `127.0.0.1:55432`
- `docker compose exec db psql -U course_user -d course_db -c "SELECT 1;"` — ответ `1`

## Остановка
`docker compose down`