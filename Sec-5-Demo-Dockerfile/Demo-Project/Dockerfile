# Use python base image with an explicit Alpine version
FROM python:3.12-alpine3.18

# OCI Labels
LABEL org.opencontainers.image.authors="Mihir Modi"
LABEL org.opencontainers.image.title="Demo: ARG vs ENV in Docker"
LABEL org.opencontainers.image.description="A Dockerfile demo illustrating the difference between ARG (build-time) and ENV (runtime) instructions"
LABEL org.opencontainers.image.version="1.0"

# Define build-time argument for environment (defaults to "dev")
ARG ENVIRONMENT=dev

# Set the ENV variable using the ARG value
ENV APP_ENVIRONMENT=${ENVIRONMENT}

# Refresh repositories and install dependencies
RUN apk update && apk add --no-cache ca-certificates build-base

# Set working directory and install dependencies
WORKDIR /app

# Copy requirements and install Python dependencies
COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY app.py .
COPY templates/ ./templates

# Build-time log
RUN echo "Building for env: ${APP_ENVIRONMENT}"

# Start the Flask app
CMD ["python3", "app.py"]


# Run Dockerfile 
# docker build -t <abc-build:v1> .
# docker run --name <> -p 8080:80 -d <abc-build:v1>
