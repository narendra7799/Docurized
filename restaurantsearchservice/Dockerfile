
FROM maven:3.6-jdk-8-alpine as build
ADD ./ app/
WORKDIR /app
RUN mvn install

FROM openjdk:8-jdk-alpine
COPY --from=build /app/target/restaurantsearchservice-*.jar restaurantsearchservice.jar
EXPOSE 8081
ENTRYPOINT ["java","-jar","restaurantsearchservice.jar"]