FROM openjdk:24-ea-16-jdk-slim-bullseye

# Set the working directory inside the container
WORKDIR /app

# Copy the application JAR file into the container.  We assume it's built and present
# Adjust the path as needed if your build process outputs the JAR to a different location.
COPY target/spring-xd-elasticsearch-sink-0.0.1-SNAPSHOT.jar app.jar

# Expose the port the application listens on (adjust as needed)
EXPOSE 8080

# Run the application
ENTRYPOINT ["java","-jar","app.jar"]