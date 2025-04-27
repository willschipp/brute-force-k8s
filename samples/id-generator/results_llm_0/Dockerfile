FROM openjdk:24-ea-16-jdk-slim-bullseye

# Set working directory
WORKDIR /app

# Copy the project
COPY ./target/id-generator-0.0.1-SNAPSHOT.jar  id-generator.jar

# Expose port (adjust if needed)
EXPOSE 8080

# Run the application
CMD ["java", "-jar", "id-generator.jar"]