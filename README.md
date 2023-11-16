# Docker
**:memo:Docker Notes**

**:page_facing_up:Docker Terminologies**

1) **Docker File** - It contains Docker Domain Specific keywords to build image
2) **Docker Image** - It is a package which contains everything (App code + softwares + env + libraries)
3) **Docker Container** - It is run time instance of Docker Image, Our application will execute in Docker container
4) **Docker Registry** - It is a place where we can store our Docker images (docker hub)
5) **Docker Engine** - It is a software using which we will create Docker images and Docker Container (docker daemon)


**:rocket:Docker Commands**

1) **docker info** -> System wide information regarding the Docker installation (sudo service docker start)
2) **docker images** -> List all the Docker images available on system
3) **docker ps** -> List all the running Docker containers
4) **docker pull <image-name>** -> Download a Docker image from a registry
5) **docker build <PATH>** -> Build an image from a Dockerfile
6) **docker run <image-name/id>** -> Create and run a new container from an image
7) **docker stop <contaier-name>** -> Stop a running container
8) **docker rmi IMAGE** -> Remove one or more Docker images
9) **docker rm CONTAINER** -> Remove one or more Docker containers
10) **docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]** -> Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
11) **docker push NAME[:TAG]** -> Upload an image to a registry
12) **docker system prun -a** -> Remove stopped contaiers and unused images  

**:fast_forward:Steps To Create a Dockerfile**
- Create a file named Dockerfile.
- Add instructions in Dockerfile.
- Build Dockerfile to create an image.
- Run the image to create a container.

![image](https://github.com/JayPansuriya/docker/assets/68367978/c12f8f80-8fad-4dc7-adbe-d6dc0b3461da)

**:page_facing_up:Docker file**

- Dockerfile contains instructions to build docker image
- In Dockerfile we use DSL (Domain Specific Language) keywords I
- Docker engine will process Dockerfile instructions from top to bottom

**Dockerfile keywords**
- **FROM:** It indicates base image to run our application. On top of base image we will create our own image.
- **MAINTAINER:** Deprecated. Used to set the author or maintainer information.
- **USER:** Sets the user or UID to use when running the container.
- **COPY:** It is used to copy files/folders to image while creating an image.
- **ADD:** Similar to COPY but can also fetch files from remote URLs and extract compressed files.
- **RUN:** Executes a command in a new layer on top of the current image and commits the results while creating an image.
- **CMD:** Provides a default command that will be executed when the container starts.
- **ENTRYPOINT:** Configures the container to run as an executable, setting the default application. It executes while creating container.
- **ENV:** Sets environment variables in the image.
- **LABEL:** Adds metadata to an image in the form of key-value pairs.
- **ARG:** Used to avoid hardcoded values in docker file.
- **WORKDIR:** Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions.
- **EXPOSE:** Informs Docker that the container listens on specified network ports at runtime.
- **VOLUME:** Creates a mount point with the specified name and marks it as holding externally mounted volumes.


