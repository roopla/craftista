FROM maven:3.8.4-eclipse-temurin-17 as build
WORKDIR /app
COPY pom.xml .
COPY src /app/src
RUN mvn package -DskipTests

FROM eclipse-temurin:17-jre-alpine
WORKDIR /app
COPY --from=build /app/target/*.jar /app/app.jar
EXPOSE 8080
CMD ["java", "-jar", "/app/app.jar"]

