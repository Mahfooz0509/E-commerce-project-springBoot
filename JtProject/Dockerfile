FROM eclipse-temurin:17-jdk-alpine

WORKDIR /app

# Copy Maven wrapper and project files
COPY mvnw .
COPY .mvn .mvn
COPY pom.xml .
COPY src src

# Build the project
RUN chmod +x mvnw && ./mvnw clean package -DskipTests

# Copy the jar to container
COPY target/*.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
