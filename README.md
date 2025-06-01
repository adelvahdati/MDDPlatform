### Create MDDPlatform Network
docker network create mddplatform

### Pull RabbitMQ, MongoDB, PlantUML form Docker Hub
docker pull rabbitmq:3-management
docker pull mongo
docker pull plantuml/plantuml-server:jetty

### Pull Api Client Image form Docker Hub
docker pull adelvahdati/apiclientservice

### Load Images From *.tar File: (Suppose that local images are stored in c:/Images Folder)
docker load -i c:/Images/conceptservice.tar
docker load -i c:/Images/problemdomainservice.tar
docker load -i c:/Images/domainservice.tar
docker load -i c:/Images/domainmodelservice.tar
docker load -i c:/Images/modeltransformationservice.tar
docker load -i c:/Images/diagramservice.tar

### Create Containers
docker compose -f docker-compose-infrastructure.yml create
docker compose -f docker-compose-service.yml create