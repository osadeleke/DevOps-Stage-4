# Use an official Maven image to build the application
FROM maven:3.8.6 AS build-stage

# Set the working directory
WORKDIR /app

# Copy the Maven project files
COPY pom.xml .
COPY src ./src

# Build the application
RUN mvn clean package -DskipTests

# Use an official OpenJDK runtime as the base image
FROM openjdk:8-jdk-alpine

# Set the working directory
WORKDIR /app

# Copy the built JAR file from the build stage
COPY --from=build-stage /app/target/users-api-0.0.1-SNAPSHOT.jar  .

# Expose port 8080
EXPOSE 8080

# Run the application
CMD ["java", "-jar", "users-api-0.0.1-SNAPSHOT.jar"]
