# Aula1

Iremos instalar a imagem no docker da aplicação petstore.

[Link do swagger](https://petstore.swagger.io/)

### Alguns Comandos

 - Help do docker: docker --help
 - Download: docker pull swaggerapi/petstore
 - Listar imagens: docker images
 - Listar containes: docker ps
 - Apagar imagem: docker rmi {image id}
 - Apagar container: docker rm {container id}
 - Parar execução do docker: docker stop {container id}
 - Criar container através da imagen: docker run {image}

### Mão na massa

 - Ex1: https://hub.docker.com/r/swaggerapi/petstore

```
docker pull swaggerapi/petstore
docker run -d -e SWAGGER_HOST=http://petstore.swagger.io  -e SWAGGER_URL=http://localhost -e SWAGGER_BASE_PATH=/v2 -p 80:8080 swaggerapi/petstore
```

 - Ex2: https://hub.docker.com/r/atlassian/jira-software

```
docker pull atlassian/jira-software
docker volume create --name jiravolume
docker run -v jiraVolume:/var/atlassian/application-data/jira --name="jira" -d -p 8080:8080 atlassian/jira-software
```