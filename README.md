# Docker
**:memo:Docker Notes**

**:page_facing_up:Docker Terminologies**

1) **Docker File** - It contains Docker Domain Specific keywords to build image
2) **Docker Image** - It is a package which contains everything (App code + softwares + env + libraries)
3) **Docker Container** - It is run time instance of Docker Image, Our application will execute in Docker container
4) **Docker Registry** - It is a place where we can store our Docker images (docker hub)
5) **Docker Engine** - It is a software using which we will create Docker images and Docker Container (docker daemon)


**:rocket:Docker Commands**

1) **docker info** -> System wide information regarding the Docker installation
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


