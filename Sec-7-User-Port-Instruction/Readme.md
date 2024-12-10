# USER Instruction

Sets the default user ot UID and group or GID for the rest of the stage.

Applies to RUN, ENTRYPOINT, AND CMD commands

**IMPORTANT NOTE:**
If a group is set only that group applies, Other groups are ignored.

**Running containers as non-root user enhances security by minimizing the potential impact of vulnerabilities.**

**By specifying a user with limited permissions, the attack surface is reduced, making it harder for malicious actors to exploit the container.**

# **Docker Port Instruction**
## Specific port
docker run --name <any name> -p 8080:80 -d <image name> host port 8080 to container port 80

## Publishing all exposed port with -P flag

- Use -P to publish all exposed ports to random high numbered host ports
- Ideal for multi-port applications where manual mapping is cumbersome.

## Random localhost assign
**docker run --name <any name> -p 80 -d <image name>**

## Capital port P 

- All the host dynamic generated 
- more than one port expose through (P)



