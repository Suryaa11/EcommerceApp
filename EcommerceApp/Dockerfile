FROM maven:3.9.6-eclipse-temurin-17 as build
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package

FROM tomcat:10.1.15-jdk17
WORKDIR /usr/local/tomcat/webapps/
COPY --from=build app/target/*.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh", "run"]
