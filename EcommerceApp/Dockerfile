FROM maven:3.9.6-eclipse-temurin-17 as build
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package


FROM eclipse-temurin:17-jre
WORKDIR /app
COPY --from=build /app/target/EcommerceApp-0.0.1-SNAPSHOT app.jar
CMD["java","-jar","app.jar"]
