https://www.youtube.com/watch?v=0uLqdBpYAVA
https://www.youtube.com/watch?v=SzbeDqBSRkc

http://localhost:8080/h2-console/ 

JDBC URL: jdbc:h2:mem:course_platform  ( we can replace if the default is shown as jdbc:h2:~/test )


-> C:\Users\shrav\Desktop\dan\hello-jdbc-master>docker login
-> C:\Users\shrav\Desktop\dan\hello-jdbc-master>docker build -t hello-jdbc .	
-> C:\Users\shrav\Desktop\dan\hello-jdbc-master>docker tag hello-jdbc nbarre/hello-jdbc
-> C:\Users\shrav\Desktop\dan\hello-jdbc-master>docker push nbarre/hello-jdbc
-> C:\Users\shrav\Desktop\dan\hello-jdbc-master>docker rmi hello-jdbc
-> C:\Users\shrav\Desktop\dan\hello-jdbc-master>docker run -p 8080:8080 nbarre/hello-jdbc


http://localhost:8080/h2-console/

Got the error: 
Sorry, remote connections ('webAllowOthers') are disabled on this server.

Added below property in application.properties to fix the above error.
spring.h2.console.settings.web-allow-others=true

References:
https://stackoverflow.com/questions/9838041/connection-has-a-remote-database


-> In google cloud console
 root@cs-943055184026-default:/home/naveen_dec29# gcloud container clusters get-credentials naveen-cluster-1 --zone us-central1-c --project clean-tower-358110

-> root@cs-943055184026-default:/home/naveen_dec29# kubectl apply -f docker-k8s-demo.yaml
W0904 00:49:05.752862     682 gcp.go:120] WARNING: the gcp auth plugin is deprecated in v1.22+, unavailable in v1.25+; use gcloud instead.
To learn more, consult https://cloud.google.com/blog/products/containers-kubernetes/kubectl-auth-changes-in-gke
deployment.apps/docker-k8s-demo-deployment created

-> In google cloud console , go to Workloads , Click Expose  , Give Target port as 8080, and select Load balancer as Service type