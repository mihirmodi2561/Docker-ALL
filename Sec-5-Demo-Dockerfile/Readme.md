## Why Use ARG and ENV Together?
- The **ARG instruction allows you to pass variables at build time without modifying the Dockerfile, making it more dynamic and reusable**.
- By combining ARG and ENV, you can pass values configured during the build process into the runtime environment of the container.
- Separation of Concerns:
**        ARG is used for build-time customization.
        ENV is used for runtime customization.**
- This separation makes the Dockerfile flexible at both stages without overlap or confusion.

# Dockerfile - ENV Instruction

- ENV sets the environment variables in our Docker image and when we run it as a container, same env variable will be persisted in our container.

What is the key difference between ENV and ARG?
ENV: ENV is persisted in the final image and will be available in container when it is run from this image.

ARG: ARG is not persisted in the final image, so no scope of using that value in container when it is run from this image.

## WORKDIR

- Sets the working directory for any RUN, CMD, ENTERYPOINT, COPY and ADD instructions that follow it in the Dockerfile.
- The WORKDIR instruction can be used multiple times in a Dockerfile

- If WORKDIR not specified, the default working directory is "/"

- If we are using the base image "FROM python", WORKDIR likely to be set by the base image. 

## CMD

- Command to run when starting a container from the image
- Only one CMD instruction is allowed per Dockerfile, if there are multiple, only the last one is used
- Used to set default commands or parameters for the container

Syntax

CMD ["executable", "param1", "param2"]
CMD ["param1",  "param2"]
CMD command param1 param2