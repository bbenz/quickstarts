# Build stage

FROM maven:3.6.0-jdk-11-slim AS build
WORKDIR /home/app/
COPY . /home/app/
RUN mvn clean install

# Package stage

FROM openjdk:11-jre-slim
COPY --from=build /home/app/target/OrderProcessingService-0.0.1-SNAPSHOT.jar /usr/local/lib/demo.jar
ENTRYPOINT ["java","-jar","/usr/local/lib/demo.jar"]
