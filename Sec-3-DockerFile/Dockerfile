From nginx

#Custom Labels

LABEL maintainer = "Mihir Modi"
LABEL version = "1.0"
LABEL description = "A single Nginx Application"

COPY index.html /usr/share/nginx/html


# docker build -t mynginx-custom:v1 .

## Docker container
# docker run --name mynginx1 -p 8090:80 -d mynginx-custom:v1

# View Image Labels?
# docker image inspect
# docker image inspect --format = '{{json.Config.Labels}}' myimage