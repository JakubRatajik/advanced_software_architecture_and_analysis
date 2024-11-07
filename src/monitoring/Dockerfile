# Starting from official base image for maven (it has both Maven and JDK) / BUILD PART
FROM maven:3.9.9-eclipse-temurin-17 AS build

# Set the working directory inside the container
WORKDIR /app

# Copy pom.xml
COPY pom.xml ./
# Copy the entire src directory from my project into /app/src in the container
COPY src ./src

# Install dependencies in the container
RUN mvn clean package


#RUNTIME PART
#Smaller image for running the compiled application
FROM eclipse-temurin:17-jdk-jammy

WORKDIR /app

COPY --from=build /app/target/*.jar app.jar

# Expose the port the app runs on
EXPOSE 8080

# The command to run your application
CMD ["java", "-jar", "app.jar"]


