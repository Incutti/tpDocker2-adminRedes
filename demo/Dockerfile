##Multi Stage
FROM eclipse-temurin:21.0.2_13-jdk-jammy AS build
WORKDIR /opt/app
COPY .mvn/ .mvn
COPY mvnw pom.xml ./
RUN ./mvnw dependency:go-offline
COPY ./src ./src
RUN ./mvnw clean install

FROM eclipse-temurin:21.0.2_13-jre-jammy AS run
WORKDIR /opt/app
EXPOSE 8080
COPY --from=build /opt/app/target/*.jar /opt/app/*.jar
ENTRYPOINT ["java", "-jar", "/opt/app/*.jar"]


##Single Stage
##FROM eclipse-temurin:21.0.2_13-jdk-jammy
##WORKDIR /app
##COPY .mvn/ .mvn
##COPY mvnw pom.xml ./
##RUN ./mvnw dependency:go-offline
##COPY src ./src
##CMD ["./mvnw", "spring-boot:run"]