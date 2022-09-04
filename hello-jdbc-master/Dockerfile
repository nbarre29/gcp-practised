FROM openjdk:8-jdk-alpine

EXPOSE 8080

ADD target/hello-jdbc.jar hello-jdbc.jar

ENTRYPOINT ["java","-jar","hello-jdbc.jar"]