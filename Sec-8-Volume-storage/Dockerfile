FROM nginx:alpine-slim

# OCI Labels
LABEL org.opencontainers.image.authors="Mihir Modi"
LABEL org.opencontainers.image.title="Demo: Populate Docker Volumes with Containers"
LABEL org.opencontainers.image.description="A Dockerfile demo illustrating how to populate Docker volumes using containers and serving static content with NGINX."
LABEL org.opencontainers.image.version="1.0"

COPY ./static-content/ /use/share/nginx/html

# Populate a Volume Using COntainer

VOLUME [ "/usr/share/nginx/html" ]

# docker run --name volum -p 8091:80 --mount type=volume, source=myvol, target= /usr/share/nginx/html