FROM openjdk:8-jdk-alpine

WORKDIR /app

# Копируем собранный JAR файл
ADD target/auth-service-1.0.0.jar app.jar

# Открываем порт 8080
EXPOSE 8080

# Запускаем приложение
CMD ["java", "-jar", "app.jar"] 