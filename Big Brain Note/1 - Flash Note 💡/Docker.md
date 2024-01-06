1. Consistency on all envionment
- `docker run`
2. Can be moved around in different stage
# Images (recipe)
code, libraries (ingredients)
runtime, system tools (instructions) 

# Containers 
where you run the images 
- this is what you created according to the recipe
One images can create a lot of containers 
# Volumes 
persistent data storage mechanism 
data that can be accessed by the containers and the host machine 
shared folder that outside the containers

# Network
different stands in the kitchen can communicate with each other
communication channel 
share information and services while maintaining isolation 

# Workflow
1. Docker Client : UI to interact with docker 
2. Docker Host (Docker Demon) : listen to docker client, carry out the instruction
3. Docker Registry (Docker Registry): Centralize repo for all the images

# Dockerfile
`FROM` : The base image to use 
`WORKDIR`
`COPY`
`RUN` : Execute the command in the shell 
`EXPOSE` : network port
`ENV` : environment variable
`ARG` : Define the build time variables
`VOLUME` : mount the external storage 
`CMD` : 
`ENTRYPOINT`: 















