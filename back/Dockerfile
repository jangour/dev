# Use an official Java runtime as a parent image
FROM openjdk:11-jre-slim

# Set the working directory in the container
WORKDIR /app

# Copy the JAR file into the container
COPY target/back.jar app.jar

# Expose the port your application listens on
EXPOSE 8082

# Define the command to run your application
CMD ["java", "-jar", "app.jar"]
