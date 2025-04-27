FROM openjdk:24-ea-16-jdk-slim-bullseye

WORKDIR /app

COPY ./target/eureka-server-1.0-SNAPSHOT.jar app.jar

EXPOSE 8761

CMD ["java","-jar","app.jar"]