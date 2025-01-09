# Use the official Maven image to build the app
FROM maven:3.8.4-openjdk-11-slim as builder

# Set the working directory
WORKDIR /app

# Copy the pom.xml and install dependencies (skip tests for faster builds)
COPY . .

RUN mvn clean install -DskipTests

# Copy the source code

# Package the application
RUN mvn clean package -DskipTests

# Use an official OpenJDK image for running the app
FROM openjdk:11-jre-slim

# Set the working directory
WORKDIR /app

# Copy the jar file from the builder stage
COPY --from=builder /app/target/*.jar app.jar

# Expose the port
EXPOSE 8761

# Run the jar file
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
