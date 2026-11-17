EXPERIMENT 3: CONTAINERIZATION OF A MICROSERVICE

OPTION A (easiest - only Docker needed)
  docker build -t app-service:v1 .
  docker run -p 8080:8080 app-service:v1
  Open http://localhost:8080/api/data

OPTION B (as in lab manual - needs JDK 17 + Maven + Docker)
  mvn clean package
  docker build -f Dockerfile.simple -t app-service:v1 .
  docker run -p 8080:8080 app-service:v1
  Open http://localhost:8080/api/data

Expected output:
  {"service":"app-service","version":"v1","message":"Hello from containerized microservice!"}

Useful commands:
  docker images | docker ps | docker logs <id> | docker stop <id>
