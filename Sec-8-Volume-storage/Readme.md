# Docker Volumes Vs Bind Mounts

# Volumes:
Volumes are the preferred mechanism for persisting data by docker containers.

- volume will be completely manged inside from the container itself.
- volume are easier to back uo or migrate than bind mounts.
- You can manage volumes using Docker CLI commands or Docker API.
- Volumes work on both Linux and Windows containers.
- Volumes can be more safely shared among multiple containers.
- Volume drivers let you store volumes on remote hosts or cloud providers, encrypt the contents of volumes, or add other functionality.
- New volumes can have their content pre-populated by a container.
- Volumes on Docker Desktop have much higher performance than bind mounts from Mac and Windows hosts.

## Name volume
docker volume create my-volume

## Inspect mode
docker volume inspect my-volume

## Remove Unused Docker volumes
docker volume prune 

## Remove Unused **all** Docker volumes
docker volume prune -a

# Volume Mount Options (--mount vs -v)
--mount --> for explicit volume mounting.

# Syntax:
<!-- --mount 
type=volume, source=volume_name, target=container_path
type=volume, source=myvol101, target= /myapps -d nginx:alpine-slim -->

<!-- docker run \
--name volume-demo2 \
-p 8090:80 \
-v myvol101:/myapps \
-d nginx:alpine-slim -->

## Popular Data in Docker volumes using containers
- Docker Image named (abc:v1) --> Contains some content at /usr/share/nginx/html
- The static content from the Docker container is copied to the volume automatically
- No data loss

## Mount volumes with Read-Only option
- Prevents containers from modifying the volume's data.
- Observation: Attempts to write to the volume within the container will fail.

<!-- 
--mount 
source=volume_name, target=container_path, readonly
source=myvol101, target= /myapps, readonly -d nginx:alpine-slim -->



# Bind Mounts:
 Bind mounts are dependent on the directory structure and os of the host machine, volumes are completely managed by Docker.



