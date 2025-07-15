# Use Java 17 base image (Eclipse Temurin)
FROM eclipse-temurin:17-jre-alpine

# Specify the JAR path as a build argument
ARG artifact=target/spring-boot-web.jar

# Create working directory
WORKDIR /opt/app

# Copy the built jar file into the image
COPY ${artifact} app.jar

# Run the application
ENTRYPOINT ["java", "-jar", "app.jar"]
