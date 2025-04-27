FROM openjdk:24-ea-16-jdk-slim-bullseye

# Set the working directory inside the container
WORKDIR /app

# Copy the application JAR file into the container.  This assumes the artifact is built and named 'app.jar'. Adjust accordingly.
COPY build/libs/app.jar app.jar

# Expose the port used by the application (adjust if necessary)
EXPOSE 8080

# Define the command to run the application
CMD ["java", "-jar", "app.jar"]