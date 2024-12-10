Docker Command - Basics

## Pull -- Docker Image from Docker Hub
docker pull mihirmodi2561/mynginx:v1

## Run -- Docker Container
docker run --name myapp1 -p 8080:80 -d mihirmodi2561/mynginx:v1

8080<local host> : 80<container Port >
where 
8080 -- local machine (host) that you access from your browser
80 -- application inside a container or server is actually listening on.

## Connect to Docker containers
docker exec -it myapp1 /bin/sh

Where: To go inside container through this command 

docker stop myapp1
docker start myapp1

## Remove Docker container
docker rm myapp1

## Remove Docker images
docker rmi mihirmodi2561/mynginx:v1

## Fetch from Docker Hub
docker pull mihirmodi2561/mynginx:v1

## To check running containers
docker ps

## To check all containers
docker ps -a

## List only container IDs
docker ps -q

## list all the environment variable.
docker exec -it myapp1 printenv

## Docker Tag 
docker tag myapp1 mihirmodi2561/mynginx:v1

# View Image Labels?
docker image inspect
docker image inspect --format = '{{json.Config.Labels}}' myimage