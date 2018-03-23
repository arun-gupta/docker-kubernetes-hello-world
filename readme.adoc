= Hello World with Docker and Kubernetes

This repo consists of a Spring Boot Hello World application. It shows:

. Run & test the application from CLI
. Create a Docker image, run the container and test it
. Create Kubernetes deployment and test it

Let's get started!

== CLI

=== Run App

```
mvn spring-boot:run
```

=== Test Application

```
curl http://localhost:8080
```

== Docker

=== Build Application

```
mvn clean package
```

=== Build Docker Image

```
docker image build -t arungupta/helloworld-spring-boot:latest .
```

=== Push Docker Image

```
docker image push arungupta/helloworld-spring-boot:latest
```

=== Run Docker Container

```
docker container run -d --name hello-world -p 8080:8080 arungupta/helloworld-spring-boot:latest
```

=== Test Application

```
curl http://localhost:8080
```

=== Delete Docker Container

```
docker container rm -f hello-world
```

== Kubernetes

=== Create Deployment

```
kubectl apply -f deployment.yaml
```

=== Test Application

```
curl http://`kubectl get svc hello-world-service -o jsonpath={.status.loadBalancer.ingress[0].hostname}`
```

=== Delete Deployment

```
kubectl delete -f deployment.yaml
```

