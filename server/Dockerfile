FROM maven:3.8.5-openjdk-8 AS builder
WORKDIR /usr/app
RUN git clone https://github.com/MTA1711/tasks-rest-api.git ./
RUN mvn clean package

FROM adoptopenjdk/openjdk8:jre8u332-b09-alpine
WORKDIR /usr/app
COPY --from=builder /usr/app/target/tasks-1.0.jar ./
EXPOSE 8080
CMD ["java", "-jar", "tasks-1.0.jar"]
