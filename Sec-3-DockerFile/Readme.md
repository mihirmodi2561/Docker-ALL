# Dockerfiles

Simple text file that contains set of instruction to build a Docker Image
Automate the process of creating Docker Images by specifying steps which are called INSTRUCTIONS in Docker terminology

Example:
Install Software
Copy files
Set environment variables
Run Commands
Define entry point for you application

# Dockerfile Label Instruction 

What is label instruction in dockerfile?
- Add metadata to an image
- An Image can have more than one label
- Labels included in the base image are inherited by your image.
- If a label already exists but with different value, the most recently applied value overrides any previously set value.


## View Image Labels? Inspect Mode
docker image inspect <image name>
docker image inspect --format = '{{json.Config.Labels}}' <image name>


## Inspect the Docker container
docker inspect [CONTAINER-NAME or CONTAINER-ID]
## Inspect the Docker image
docker image inspect [IMAGE-NAME]:[IMAGE-TAG]
## Get the creation date of the Docker image
docker inspect --format='{{.Created}}' [IMAGE-NAME]:[IMAGE-TAG]

## Get the Docker image labels (unformatted)
docker inspect --format='{{json .Config.Labels}}' [IMAGE-NAME]:[IMAGE-TAG]

## Get the Docker image labels (formatted with jq)
docker image inspect --format='{{json .Config.Labels}}' [IMAGE-NAME]:[IMAGE-TAG] | jq


# Container Inspect 
## Example:
docker inspect mylabels-demo
## Get the IP address of the container
docker inspect --format='{{.NetworkSettings.IPAddress}}' [CONTAINER-NAME or CONTAINER-ID]
## Inspect container state (running, paused, stopped)
docker inspect --format='{{.State.Status}}' [CONTAINER-NAME or CONTAINER-ID]
## Inspect exposed ports
docker inspect --format='{{json .Config.ExposedPorts}}' [CONTAINER-NAME or CONTAINER-ID]
## Inspect network details of the container (formatted with jq)
docker inspect --format='{{json .NetworkSettings}}' [CONTAINER-NAME or CONTAINER-ID] | jq
