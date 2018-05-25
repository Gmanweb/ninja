|---------|
  PROJECT
|---------|

## create a project, maven java.
create a spring project "https://start.spring.io/" (Web, Actuator)
use this hello world example
https://spring.io/guides/gs/rest-service/

## build project using maven docker image
```
docker run -v "$PWD":/project -w /project maven:3.3.9-jdk-8 mvn clean package
```

## Run from terminal
```
java -jar target/actuator-sample-0.0.1-SNAPSHOT.jar
```
## Test the service
Now that the service is up, visit http://localhost:8080/greeting, where you see:
http://localhost:8080/greeting
```
{"id":1,"content":"Hello, World!"}
```

Provide a name query string parameter with http://localhost:8080/greeting?name=User. Notice how the value of the content attribute changes from "Hello, World!" to "Hello User!":
http://localhost:8080/greeting?name=User
```
{"id":2,"content":"Hello, User!"}
```

## build image
docker build -t dockerdonegal/helloworld:v1 .

## login to docker 
https://hub.docker.com/r/dockerdonegal/
```
docker login
Username: dockerdonegal
Password: {your-docker-hub-password}
```
## push image to 
docker push dockerdonegal/helloworld:v1

## pull our image and run it.
```
docker run -it -p 8080:8080 --name actuator dockerdonegal/helloworld:v1
```

|---------|
  TESTING
|---------|

## run 
docker run -v "$PWD":/project -w /project maven:3.3.9-jdk-8 mvn test


|---------|
  JENKINS
|---------|


https://jenkins.io/doc/pipeline/tour/hello-world/