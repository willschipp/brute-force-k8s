FROM openjdk:17-jdk-slim AS builder

WORKDIR /app

COPY ./build.gradle ./settings.gradle ./gradle.properties ./gradlew ./gradlew.bat ./src ./
RUN ./gradlew build

# Stage 2: Create the runtime image
FROM openjdk:17-jdk-slim

WORKDIR /app

COPY --from=builder /app/build/libs/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]