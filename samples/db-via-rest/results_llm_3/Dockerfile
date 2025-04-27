FROM openjdk:24-ea-16-jdk-slim-bullseye

# Set the working directory inside the container
WORKDIR /app

# Copy the application JAR file into the container
COPY build/libs/*.jar app.jar

# Expose the port the application will listen on (adjust if needed)
EXPOSE 8080

# Define the command to run the application
CMD ["java", "-jar", "app.jar"]