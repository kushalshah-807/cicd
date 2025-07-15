# Use Java 17 base image (Eclipse Temurin)
FROM eclipse-temurin:17-jre-alpine

# Create user with UID 111 and GID 113 and home directory
RUN addgroup -g 113 jenkins && \
    adduser -u 111 -G jenkins -h /home/jenkinsuser -D jenkinsuser

# Set environment variables and working directory for the new user
ENV HOME=/home/jenkinsuser
WORKDIR /home/jenkinsuser

# Specify the JAR path as a build argument
ARG artifact=target/spring-boot-web.jar

# Copy the built jar file into the image
COPY ${artifact} app.jar

# Change ownership of copied file to jenkinsuser
RUN chown jenkinsuser:jenkins app.jar

# Switch to the new user
USER 111:113

# Run the application
ENTRYPOINT ["java", "-jar", "app.jar"]
