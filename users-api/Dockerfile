FROM maven:3.8.5-openjdk-8 AS build

WORKDIR /app

COPY pom.xml .
COPY src ./src

RUN mvn clean package -DskipTests

FROM openjdk:8-jdk-alpine

COPY --from=build /app/target/users-api-0.0.1-SNAPSHOT.jar /usr/app/users-api.jar

WORKDIR /usr/app

EXPOSE 8083

CMD ["java", "-jar", "users-api.jar"]
