FROM openjdk:8-jdk-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the application JAR file into the container
COPY build/libs/*.jar app.jar

# Expose the port the application runs on (adjust if needed)
EXPOSE 8080

# Define the command to run the application
CMD ["java", "-jar", "app.jar"]