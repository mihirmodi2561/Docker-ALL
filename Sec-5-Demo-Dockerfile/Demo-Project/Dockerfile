# Use python base image
FROM python:3.12-alpine

# OCI Labels
LABEL org.opencontainers.image.authors="Mihir Modi"
LABEL org.opencontainers.image.title="Demo: ARG vs ENV in Docker"
LABEL org.opencontainers.image.description="A Dockerfile demo illustrating the difference between ARG (build-time) and ENV (runtime) instructions"
LABEL org.opencontainers.image.version="1.0"

# Define build-time argument for environment (defaults to "dev")
ARG ENVIRONMENT=dev

#Runtime 
# Set the ENV variable using the ARG value
ENV APP_ENVIRONMENT=${ENVIRONMENT}

RUN apk add --no-cache python3 py3-pip build-base musl-dev python3-dev

# Set working directory and install dependencies
WORKDIR /app

# copy requirements and install dependency
COPY requirements.txt requirements.txt

RUN pip install -r requirements.txt 

# Copy application code
COPY app.py .

COPY templates/ ./templates

RUN echo "Building for env: ${APP_ENVIRONMENT}"

# Start the Flask app
CMD [ "python3" "app.py" ]


# Run Dockerfile 
# docker build -t <abc-build:v1> .
# docker run --name <> -p 8080:80 -d <abc-build:v1>
