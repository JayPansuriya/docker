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
12) **docker system prune -a** -> Remove stopped contaiers and unused images  

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

**Docker Volumes**
- Docker volumes are used to persist the data generated by Docker containers
- Using Docker volume we can de-couple data storage from Docker container
- Using Docker volume we can share the data among multiple Docker containers
- On deletion of Continer Docker Volume will not be deleted

**Docker Volume Commands**

- **docker volume --help** -> To display docker volume commands
- **docker volume <volume-name>** -> Create Docker Volume 
- **docker volume ls** -> Display Docker volumes 
- **docker volume inspect <volume-name>** ->  Inspect the volume 
- **docker volume rm <volumne-name>** -> Remove docker volume 
- **docker volume prune** -> Remove unsued volumes 

**Ex:** docker run -d --name=webapp20 --mount source=new_vol,destination=/usr/share/nginx/html -p 80:80 nginx

**Docker Compose**

- Docker compose is a tool that is used to manage multi-container-based applications
- We will give input to Docker compose tool using the YAML file to run multiple containers

**:page_facing_up:Sample Docker Compose YML (docker-compose.yml)**
version:
services
network:
volumes:

**Docker Compose Commands**
- **docker-compose up** -> Create and start the containers
- **docker-compose ps** -> List Docker containers started by docker compose
- **docker-compose down** -> Stop and remove containers
- **docker-compose images** -> list down running container images
- **docker-compose -f <filename> up** ->  Using different file


**Docker Network**
- Networking is all about communication among processes
- Docker Networking enables a user to link a docker container to as many networks as they require
- Docker network is used to provide complete isolation for Docker containers
  
**Advantages of Docker Networking**
1) They share single operating system and maintains containers in isolated manner
2) It requries fewer OS instance to run the workload
3) It helps in fast delivery of the software
4) It helps in application portability

- When Docker s/w is installed in a machine, by default, three docker networks will be configured
1) none 2) host 3) bridge
Note: One container we can attach to multiple networks
-> When container is attached to multiple networks then those containers can communicate
-> Docker providing Networking to containers using Network Drivers

**Docker Network Drivers**
1) Bridge
2) Host
3) None
4) Overlay
5) Macvlan

**Bridge Driver** 
- This is the default network drive created on the Docker host machine
Note: Bridge network drivers are very useful when an application running in a standalone container

**Host Driver**
 It is useful when a standalone container is available
- The container will not get any IP address when we enable Host Driver
Note: For example a container is executed that binds to port 80 with Host Network Driver. In this case we no need to map container port to host machine port.
-> This is useful when we are running our containers with large no. of ports
  
**None Driver**
- In this type of network, the containers will have no access to the network
  
**Overlay Driver**
- Use in Docker Swarm to orchestrate our Docker containers
- Overlay Driver will be used when we have a Docker Swarm cluster
  
**Macvlan Driver**
- This network driver will assign a MAC address to a container
- MAC address will make our device as Physical
- Using this MAC address Docker engine routes the traffic to a particular route
- Macvlan driver simplifies communication between container


**:rocket:Docker Swarm**

- It is a container orchestration sofware
- Orchestration means managing processes/containers
- Docker Swarm is used to setup Docker Cluster
- Docker swarm is embedded in Docker engine
- Cluster means group of servers
- We will setup Master and Worker nodes using Docker Swarm cluster
- Master will schedule the tasks (containers) and manage the nodes and node failures
- Worker nodes will perform the action (containers will run here)

**Swarm Features**
1) Cluster Management 2) Decentralize design 3) Declarative service model
4) Scaling 5) Multi Host Network 6) Service Discovery
7) Load Balancing 8) Secure by default 9) Rolling Updates
