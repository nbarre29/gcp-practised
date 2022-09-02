https://www.youtube.com/watch?v=0zJUK-SwPqQ&t=938s (Deploy Microservice(Spring Boot Application ) in Google Cloud | Java Techie)
https://www.youtube.com/watch?v=qx_T6-EKkBE (Deploy a Spring Boot Application to App Engine Java 11)
https://github.com/Java-Techie-jt

https://github.com/Java-Techie-jt/Spring-Cloud-Foundry
https://github.com/Java-Techie-jt/Spring-Cloud-Foundry.git




First run locally and test:
C:\Users\shrav\Desktop\spring-boot-gcp>mvn clean install
C:\Users\shrav\Desktop\spring-boot-gcp>mvn spring-boot:run
http://localhost:8080/





C:\Users\shrav\AppData\Local\Google\Cloud SDK>gcloud config set project clean-tower-358110
C:\Users\shrav\AppData\Local\Google\Cloud SDK>cd C:\Users\shrav\Desktop\spring-boot-gcp
C:\Users\shrav\Desktop\spring-boot-gcp>mvn clean install
C:\Users\shrav\Desktop\spring-boot-gcp>gcloud app deploy target/spring-gcp-example-0.0.1-SNAPSHOT.jar --version 1
C:\Users\shrav\Desktop\spring-boot-gcp>gcloud app deploy target\spring-gcp-example-0.0.1-SNAPSHOT.jar --version 2