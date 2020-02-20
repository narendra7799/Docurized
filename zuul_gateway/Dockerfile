FROM maven:3.6-jdk-8-alpine as build
ADD ./ app/
WORKDIR /app
RUN mvn install

FROM openjdk:8-jdk-alpine
COPY --from=build /app/target/zuul_gateway-0.0.1-SNAPSHOT.jar zuul_gateway.jar
EXPOSE 8083
ENTRYPOINT ["java","-jar","zuul_gateway.jar"]