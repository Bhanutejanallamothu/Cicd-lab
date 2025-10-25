FROM maven:3.9.9-eclipse-temurin-17

WORKDIR /app

COPY pom.xml .
RUN mvn dependency:go-offline -B

COPY src ./src

RUN rm -rf /root/.m2/repository/io/jsonwebtoken && \
    mvn clean package -DskipTests

EXPOSE 8081
ENTRYPOINT ["java", "-jar", "target/carrental-0.0.1-SNAPSHOT.jar"]
