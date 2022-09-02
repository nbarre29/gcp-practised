https://www.youtube.com/watch?v=SzbeDqBSRkc

https://docs.docker.com/desktop/install/windows-install/
https://github.com/docker/for-win/issues/12576
https://docs.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package
https://i.stack.imgur.com/Nhxgb.png

C:\Users\shrav\AppData\Roaming\Docker\settings.json
Set "wslEngineEnabled": false

____________________________________________________________

-> 1) First, clone a repository
The Getting Started project is a simple GitHub repository which contains everything you need to build an image and run it as a container.

Clone the repository by running Git in a container.

PS C:\Users\shrav> docker run --name repo alpine/git clone https://github.com/docker/getting-started.git
Unable to find image 'alpine/git:latest' locally
latest: Pulling from alpine/git
213ec9aee27d: Pull complete
fd2d85b6e65f: Pull complete
72ec27a2c987: Pull complete
Digest: sha256:7b9c96bea8268579e925b17170ae208788e90d508ec334421384913ba61cd610
Status: Downloaded newer image for alpine/git:latest
Cloning into 'getting-started'...
PS C:\Users\shrav> docker cp repo:/git/getting-started/ .
PS C:\Users\shrav>

-> 2) Now, build the image
A Docker image is a private file system just for your container. It provides all the files and code your container needs.


PS C:\Users\shrav> cd getting-started
PS C:\Users\shrav\getting-started> docker build -t docker101tutorial .

-> 3) Run your first container
Start a container based on the image you built in the previous step. Running a container launches your application with private resources, securely isolated from the rest of your machine.

PS C:\Users\shrav\getting-started> docker run -d -p 80:80 --name docker-tutorial docker101tutorial
b2f991a24cb494ac2285330caabf1dd24fe6059f6728a438ca4c78187f0794af

-> 4) Now save and share your image
Save and share your image on Docker Hub to enable other users to easily download and run the image on any destination machine.

PS C:\Users\shrav\getting-started> docker tag docker101tutorial nbarre/docker101tutorial 
PS C:\Users\shrav\getting-started> docker push nbarre/docker101tutorial

See what you've saved on Hub



PS C:\Users\shrav> docker run --name repo alpine/git clone https://github.com/docker/getting-started.git
Unable to find image 'alpine/git:latest' locally
latest: Pulling from alpine/git
213ec9aee27d: Pull complete
fd2d85b6e65f: Pull complete
72ec27a2c987: Pull complete
Digest: sha256:7b9c96bea8268579e925b17170ae208788e90d508ec334421384913ba61cd610
Status: Downloaded newer image for alpine/git:latest
Cloning into 'getting-started'...
PS C:\Users\shrav> docker cp repo:/git/getting-started/ .
PS C:\Users\shrav> cd getting-started
PS C:\Users\shrav\getting-started> docker build -t docker101tutorial .
[+] Building 29.7s (28/28) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                  0.1s
 => => transferring dockerfile: 1.12kB                                                                                                                0.0s
 => [internal] load .dockerignore                                                                                                                     0.1s
 => => transferring context: 52B                                                                                                                      0.0s
 => [internal] load metadata for docker.io/library/nginx:alpine                                                                                       1.3s
 => [internal] load metadata for docker.io/library/python:alpine                                                                                      1.2s
 => [internal] load metadata for docker.io/library/node:12-alpine                                                                                     1.3s
 => [auth] library/python:pull token for registry-1.docker.io                                                                                         0.0s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                                                          0.0s
 => [auth] library/node:pull token for registry-1.docker.io                                                                                           0.0s
 => [base 1/4] FROM docker.io/library/python:alpine@sha256:0c46c7f15ee201a2e2dc3579dbc302f989a20b1283e67f884941e071372eb2cc                           8.7s
 => => resolve docker.io/library/python:alpine@sha256:0c46c7f15ee201a2e2dc3579dbc302f989a20b1283e67f884941e071372eb2cc                                0.0s
 => => sha256:5b4e425e03038da758a35dc6f4473b4cf9bbadb9a7cdc2766d5d1d10ef1c9ca9 1.37kB / 1.37kB                                                        0.0s
 => => sha256:ce4168535f3061a90d9588745074d3944690aaf1b882123d44e74be6e87eae7f 7.03kB / 7.03kB                                                        0.0s
 => => sha256:0c46c7f15ee201a2e2dc3579dbc302f989a20b1283e67f884941e071372eb2cc 1.65kB / 1.65kB                                                        0.0s
 => => sha256:6b2a141cd2277284ebaafc76d13b42cf8a7682e4663298a2a730f18331a95eb6 681.40kB / 681.40kB                                                    1.5s
 => => extracting sha256:6b2a141cd2277284ebaafc76d13b42cf8a7682e4663298a2a730f18331a95eb6                                                             0.2s
 => => sha256:a292fad6b52eab6b925b41e777019dceed76ce6965db16c78528bcc05f32691a 12.51MB / 12.51MB                                                      7.3s
 => => sha256:4593e4e33a591c85925982423bc77b03d1a8890b4d36780365243fe6e35db60e 231B / 231B                                                            2.1s
 => => sha256:9fc487f386544a636bd7edc089e9591a048401d4bd3011b10eef42b4393771e9 3.04MB / 3.04MB                                                        3.6s
 => => extracting sha256:a292fad6b52eab6b925b41e777019dceed76ce6965db16c78528bcc05f32691a                                                             0.7s
 => => extracting sha256:4593e4e33a591c85925982423bc77b03d1a8890b4d36780365243fe6e35db60e                                                             0.0s
 => => extracting sha256:9fc487f386544a636bd7edc089e9591a048401d4bd3011b10eef42b4393771e9                                                             0.3s
 => [internal] load build context                                                                                                                     0.2s
 => => transferring context: 10.45MB                                                                                                                  0.1s
 => [stage-6 1/3] FROM docker.io/library/nginx:alpine@sha256:082f8c10bd47b6acc8ef15ae61ae45dd8fde0e9f389a8b5cb23c37408642bf5d                         8.2s
 => => resolve docker.io/library/nginx:alpine@sha256:082f8c10bd47b6acc8ef15ae61ae45dd8fde0e9f389a8b5cb23c37408642bf5d                                 0.0s
 => => sha256:2959a35e1b1e61e2419c01e0e457f75497e02d039360a658b66ff2d4caab19c4 1.57kB / 1.57kB                                                        0.0s
 => => sha256:804f9cebfdc58964d6b25527e53802a3527a9ee880e082dc5b19a3d5466c43b7 8.89kB / 8.89kB                                                        0.0s
 => => sha256:082f8c10bd47b6acc8ef15ae61ae45dd8fde0e9f389a8b5cb23c37408642bf5d 1.65kB / 1.65kB                                                        0.0s
 => => sha256:2546ae67167b3580b7dcc4a4d56e504594bac17e22e046b2d215fc2d021d6d7e 7.40MB / 7.40MB                                                        6.9s
 => => sha256:23b845224e138d383175fc5fb15d93ad0795468b8d6210edf3a50f23ded3ed8b 601B / 601B                                                            7.1s
 => => extracting sha256:2546ae67167b3580b7dcc4a4d56e504594bac17e22e046b2d215fc2d021d6d7e                                                             0.4s
 => => sha256:9bd5732789a330a86ed2257e6bf18928c6ae873107ef0a408f1ad65b42f6d14f 894B / 894B                                                            7.3s
 => => sha256:328309e59ded59f3fc9eb5ade5c0135ec9aae5553ab837ed763fc1510799bae8 666B / 666B                                                            7.4s
 => => sha256:b231d02e51502ce72ff0813057a12b7778148c2e629aa21fe30d1cb1d0d5671b 1.40kB / 1.40kB                                                        7.5s
 => => extracting sha256:23b845224e138d383175fc5fb15d93ad0795468b8d6210edf3a50f23ded3ed8b                                                             0.0s
 => => extracting sha256:9bd5732789a330a86ed2257e6bf18928c6ae873107ef0a408f1ad65b42f6d14f                                                             0.0s
 => => extracting sha256:328309e59ded59f3fc9eb5ade5c0135ec9aae5553ab837ed763fc1510799bae8                                                             0.0s
 => => extracting sha256:b231d02e51502ce72ff0813057a12b7778148c2e629aa21fe30d1cb1d0d5671b                                                             0.0s
 => [app-base 1/5] FROM docker.io/library/node:12-alpine@sha256:d4b15b3d48f42059a15bd659be60afe21762aae9d6cbea6f124440895c27db68                     11.9s
 => => resolve docker.io/library/node:12-alpine@sha256:d4b15b3d48f42059a15bd659be60afe21762aae9d6cbea6f124440895c27db68                               0.0s
 => => sha256:d4b15b3d48f42059a15bd659be60afe21762aae9d6cbea6f124440895c27db68 1.43kB / 1.43kB                                                        0.0s
 => => sha256:4517380049fc3c9aacceae7764fcf3500354b0ac8a47e4afb35b5bbeb75b9498 1.16kB / 1.16kB                                                        0.0s
 => => sha256:bb6d28039b8cec9aa8d9032f9aa640a792a60c2cb1644691627bf046aab27c8b 6.58kB / 6.58kB                                                        0.0s
 => => sha256:df9b9388f04ad6279a7410b85cedfdcb2208c0a003da7ab5613af71079148139 2.81MB / 2.81MB                                                        0.8s
 => => sha256:3bf6d738020517f4622814e8c21db4b4aaa78ae7cab4e4f872c11696886c6285 24.91MB / 24.91MB                                                      9.8s
 => => sha256:7939e601ee5e4737cf7fdb6d1dfe31ca4c2697109290462f694710761450aef0 2.36MB / 2.36MB                                                        1.8s
 => => extracting sha256:df9b9388f04ad6279a7410b85cedfdcb2208c0a003da7ab5613af71079148139                                                             0.2s
 => => sha256:31f0fb9de071269230cb0f786012ae4e81d26e489b1fe922e57b5201e6bc9ab0 451B / 451B                                                            1.1s
 => => extracting sha256:3bf6d738020517f4622814e8c21db4b4aaa78ae7cab4e4f872c11696886c6285                                                             1.5s
 => => extracting sha256:7939e601ee5e4737cf7fdb6d1dfe31ca4c2697109290462f694710761450aef0                                                             0.1s
 => => extracting sha256:31f0fb9de071269230cb0f786012ae4e81d26e489b1fe922e57b5201e6bc9ab0                                                             0.0s
 => [base 2/4] WORKDIR /app                                                                                                                           0.2s
 => [base 3/4] COPY requirements.txt .                                                                                                                0.1s
 => [base 4/4] RUN pip install -r requirements.txt                                                                                                   17.1s
 => [app-base 2/5] WORKDIR /app                                                                                                                       0.2s
 => [app-base 3/5] COPY app/package.json app/yarn.lock ./                                                                                             0.1s
 => [app-base 4/5] COPY app/spec ./spec                                                                                                               0.1s 
 => [app-base 5/5] COPY app/src ./src                                                                                                                 0.1s
 => [app-zip-creator 1/4] COPY app/package.json app/yarn.lock ./                                                                                      0.1s 
 => [app-zip-creator 2/4] COPY app/spec ./spec                                                                                                        0.1s
 => [app-zip-creator 3/4] COPY app/src ./src                                                                                                          0.1s 
 => [app-zip-creator 4/4] RUN apk add zip &&     zip -r /app.zip /app                                                                                 2.7s
 => [stage-6 2/3] COPY --from=app-zip-creator /app.zip /usr/share/nginx/html/assets/app.zip                                                           0.1s 
 => [build 1/2] COPY . .                                                                                                                              0.1s
 => [build 2/2] RUN mkdocs build                                                                                                                      1.7s
 => [stage-6 3/3] COPY --from=build /app/site /usr/share/nginx/html                                                                                   0.1s
 => exporting to image                                                                                                                                0.1s
 => => exporting layers                                                                                                                               0.1s
 => => writing image sha256:e3db475a5c0b4d147bf6c1972d61de8fd7d1ef60b1326ed105b1e9b7a0ecbfa0                                                          0.0s 
 => => naming to docker.io/library/docker101tutorial                                                                                                  0.0s 

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
PS C:\Users\shrav\getting-started> docker run -d -p 80:80 --name docker-tutorial docker101tutorial
b2f991a24cb494ac2285330caabf1dd24fe6059f6728a438ca4c78187f0794af
PS C:\Users\shrav\getting-started> docker tag docker101tutorial nbarre/docker101tutorial 
PS C:\Users\shrav\getting-started> docker push nbarre/docker101tutorial
Using default tag: latest
The push refers to repository [docker.io/nbarre/docker101tutorial]
e3f0f3307048: Pushed
543697fdda67: Pushed
bf4e176a4d9b: Mounted from library/nginx
a1d571e4e83d: Mounted from library/nginx
6d97b4d00719: Mounted from library/nginx
2a7647ca3937: Mounted from library/nginx
549c42eea4a6: Mounted from library/nginx
994393dc58e7: Mounted from library/nginx
latest: digest: sha256:64ce715a033621fd08169a425822401ea3312aebed59e13ffe0f43718fd65027 size: 1990
PS C:\Users\shrav\getting-started>
____________________________________________________________


-> C:\Users\shrav>docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

____________________________________________________________

-> C:\Users\shrav>docker images
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
hello-world   latest    feb5d9fea6a5   11 months ago   13.3kB

-> C:\Users\shrav>docker login
Authenticating with existing credentials...
Login Succeeded

Logging in with your password grants your terminal complete access to your account.
For better security, log in with a limited-privilege personal access token. Learn more at https://docs.docker.com/go/access-tokens/


-> C:\D\Naveen\Softwares\sts-workspaces\javasamples\docker-demo>docker build -t docker-demo .
Sending build context to Docker daemon  18.26MB
Step 1/4 : FROM openjdk:8-jdk-alpine
8-jdk-alpine: Pulling from library/openjdk
e7c96db7181b: Pull complete
f910a506b6cb: Pull complete
c2274a1a0e27: Pull complete
Digest: sha256:94792824df2df33402f201713f932b58cb9de94a0cd524164a0f2283343547b3
Status: Downloaded newer image for openjdk:8-jdk-alpine
 ---> a3562aa0b991
Step 2/4 : EXPOSE 8080
 ---> Running in aafb964949ea
Removing intermediate container aafb964949ea
 ---> 013de802a853
Step 3/4 : ADD target/docker-demo.jar docker-demo.jar
 ---> 8731ac9c97cb
Step 4/4 : ENTRYPOINT ["java","-jar","docker-demo.jar"]
 ---> Running in 809d068d864d
Removing intermediate container 809d068d864d
 ---> d3b0178c0881
Successfully built d3b0178c0881
Successfully tagged docker-demo:latest
SECURITY WARNING: You are building a Docker image from Windows against a non-Windows Docker host. All files and directories added to build context will have '-rwxr-xr-x' permissions. It is recommended to double check and reset permissions for sensitive files and directories.

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them


-> C:\D\Naveen\Softwares\sts-workspaces\javasamples\docker-demo>docker images
REPOSITORY    TAG            IMAGE ID       CREATED             SIZE
docker-demo   latest         d3b0178c0881   About an hour ago   123MB
hello-world   latest         feb5d9fea6a5   11 months ago       13.3kB
openjdk       8-jdk-alpine   a3562aa0b991   3 years ago         105MB

-> C:\D\Naveen\Softwares\sts-workspaces\javasamples\docker-demo>docker tag docker-demo nbarre/docker-demo

-> C:\D\Naveen\Softwares\sts-workspaces\javasamples\docker-demo>docker push nbarre/docker-demo
Using default tag: latest
The push refers to repository [docker.io/nbarre/docker-demo]
bc00d5b1ccff: Pushed
ceaf9e1ebef5: Mounted from library/openjdk
9b9b7f3d56a0: Mounted from library/openjdk
f1b5933fe4b5: Mounted from library/openjdk
latest: digest: sha256:b9742a85aabd430c6e61e4f04cf86a951a2ede7cd00a8c77387763e2973f99e3 size: 1159

-> C:\D\Naveen\Softwares\sts-workspaces\javasamples\docker-demo>docker images
REPOSITORY           TAG            IMAGE ID       CREATED             SIZE
docker-demo          latest         d3b0178c0881   About an hour ago   123MB
nbarre/docker-demo   latest         d3b0178c0881   About an hour ago   123MB
hello-world          latest         feb5d9fea6a5   11 months ago       13.3kB
openjdk              8-jdk-alpine   a3562aa0b991   3 years ago         105MB

-> C:\D\Naveen\Softwares\sts-workspaces\javasamples\docker-demo>docker rmi docker-demo
Untagged: docker-demo:latest

-> C:\D\Naveen\Softwares\sts-workspaces\javasamples\docker-demo>docker images
REPOSITORY           TAG            IMAGE ID       CREATED             SIZE
nbarre/docker-demo   latest         d3b0178c0881   About an hour ago   123MB
hello-world          latest         feb5d9fea6a5   11 months ago       13.3kB
openjdk              8-jdk-alpine   a3562aa0b991   3 years ago         105MB

-> C:\D\Naveen\Softwares\sts-workspaces\javasamples\docker-demo>docker run -p 8080:8080 nbarre/docker-demo

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.1.0.RELEASE)

2022-09-01 23:01:38.977  INFO 1 --- [           main] com.naveen.learn.DockerDemoApplication   : Starting DockerDemoApplication v0.0.1-SNAPSHOT on 67334e3b7682 with PID 1 (/docker-demo.jar started by root in /)
2022-09-01 23:01:38.982  INFO 1 --- [           main] com.naveen.learn.DockerDemoApplication   : No active profile set, falling back to default profiles: default
2022-09-01 23:01:40.857  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-09-01 23:01:40.890  INFO 1 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-09-01 23:01:40.890  INFO 1 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/9.0.12
2022-09-01 23:01:40.907  INFO 1 --- [           main] o.a.catalina.core.AprLifecycleListener   : The APR based Apache Tomcat Native library which allows optimal performance in production environments was not found on the java.library.path: [/usr/lib/jvm/java-1.8-openjdk/jre/lib/amd64/server:/usr/lib/jvm/java-1.8-openjdk/jre/lib/amd64:/usr/lib/jvm/java-1.8-openjdk/jre/../lib/amd64:/usr/java/packages/lib/amd64:/usr/lib64:/lib64:/lib:/usr/lib]
2022-09-01 23:01:41.002  INFO 1 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-09-01 23:01:41.002  INFO 1 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1949 ms
2022-09-01 23:01:41.528  INFO 1 --- [           main] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'characterEncodingFilter' to: [/*]
2022-09-01 23:01:41.529  INFO 1 --- [           main] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'webMvcMetricsFilter' to: [/*]
2022-09-01 23:01:41.529  INFO 1 --- [           main] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
2022-09-01 23:01:41.529  INFO 1 --- [           main] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'formContentFilter' to: [/*]
2022-09-01 23:01:41.529  INFO 1 --- [           main] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'requestContextFilter' to: [/*]
2022-09-01 23:01:41.529  INFO 1 --- [           main] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'httpTraceFilter' to: [/*]
2022-09-01 23:01:41.530  INFO 1 --- [           main] o.s.b.w.servlet.ServletRegistrationBean  : Servlet dispatcherServlet mapped to [/]
2022-09-01 23:01:41.754  INFO 1 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2022-09-01 23:01:42.307  INFO 1 --- [           main] o.s.b.a.e.web.EndpointLinksResolver      : Exposing 2 endpoint(s) beneath base path '/actuator'
2022-09-01 23:01:42.438  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-09-01 23:01:42.449  INFO 1 --- [           main] com.naveen.learn.DockerDemoApplication   : Started DockerDemoApplication in 3.9 seconds (JVM running for 4.459)



-> Now we can test it,  http://localhost:8080/test-docker

naveen_dec29@cloudshell:~ (clean-tower-358110)$ gcloud container clusters get-credentials naveen-cluster-1 --zone us-central1-c --project clean-tower-358110
Fetching cluster endpoint and auth data.
kubeconfig entry generated for naveen-cluster-1.


-> naveen_dec29@cloudshell:~ (clean-tower-358110)$ sudo su
root@cs-943055184026-default:/home/naveen_dec29# ls
docker-k8s-demo.yaml  policy.json  README-cloudshell.txt
root@cs-943055184026-default:/home/naveen_dec29# kubectl apply -f docker-k8s-demo.yaml
The connection to the server localhost:8080 was refused - did you specify the right host or port?
root@cs-943055184026-default:/home/naveen_dec29# kubectl apply -f docker-k8s-demo.yaml
The connection to the server localhost:8080 was refused - did you specify the right host or port?
root@cs-943055184026-default:/home/naveen_dec29#

-> After seeing the above I just disonnected cloudshell and connected again and it worked.


-> root@cs-943055184026-default:/home/naveen_dec29# kubectl apply -f docker-k8s-demo.yaml
W0901 23:26:35.438837     714 gcp.go:120] WARNING: the gcp auth plugin is deprecated in v1.22+, unavailable in v1.25+; use gcloud instead.
To learn more, consult https://cloud.google.com/blog/products/containers-kubernetes/kubectl-auth-changes-in-gke
deployment.apps/docker-k8s-demo-deployment created