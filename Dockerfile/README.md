# Dockerfile для Spring Boot приложения авторизации

Этот проект содержит Dockerfile и docker-compose.yml для Spring Boot приложения авторизации.

## Структура проекта

- `Dockerfile` - Dockerfile для создания образа приложения
- `docker-compose.yml` - манифест для удобного запуска контейнера
- `pom.xml` - Maven конфигурация проекта
- `src/` - исходный код Spring Boot приложения
- `target/` - собранный JAR файл

## Шаги выполнения

### Шаг 1: Сборка JAR файла
```bash
mvn clean package
```

### Шаг 2: Сборка Docker образа
```bash
docker build -t auth-service .
```

### Шаг 3: Запуск с помощью docker-compose
```bash
docker compose up
```

## Конфигурация

### Dockerfile
- Базовый образ: `openjdk:8-jdk-alpine`
- Порт: 8080
- JAR файл: `target/auth-service-1.0.0.jar`

### docker-compose.yml
- Сервис: `auth-service`
- Порт: 8080:8080 (хост:контейнер)
- Сборка: `build: ./`

## Использование

После запуска приложение будет доступно по адресу: http://localhost:8080

## API Endpoints

- `GET /auth` - проверка авторизации
- `POST /auth` - авторизация пользователя 