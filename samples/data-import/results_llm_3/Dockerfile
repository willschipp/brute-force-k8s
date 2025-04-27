FROM openjdk:24-ea-16-jdk-slim-bullseye

WORKDIR /app

COPY target/data-import-0.0.1-SNAPSHOT.war /app/data-import.war

CMD ["java", "-jar", "/app/data-import.war"]