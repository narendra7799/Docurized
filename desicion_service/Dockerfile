FROM maven:3.6-jdk-8-alpine as build
ADD ./ app/
WORKDIR /app
RUN mvn install

FROM openjdk:8-jdk-alpine
COPY --from=build /app/target/desicion_service-0.0.1-SNAPSHOT.jar desicion_service.jar
EXPOSE 8761
ENTRYPOINT ["java","-jar","desicion_service.jar"]