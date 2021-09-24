# Welcome to Docker Tutorial

## What is Docker?

Docker is an ecosystem of several tools which helps to build and run containerized application. Following are some of the tools that docker hosts.

<img src ="https://user-images.githubusercontent.com/20486206/134521036-a743d1ae-19c7-4e07-a415-18b03fac6063.png" width="500" height="500"/>

## Why we should use docker?

- It helps to install a software without any hustle as the docker image contains all the dependencies and the config files required to run the installer.
- It enables the user to have multiple version of a single library in the system. 
  <img src ="https://user-images.githubusercontent.com/20486206/134533121-daf16f8a-7652-4bc5-9fc1-4695f8e01860.png" width="500" height="500"/>


## What is the idea behind docker?

Docker uses the concept of namespace segregation principal.

<img src ="https://user-images.githubusercontent.com/20486206/134533228-f20995b1-912f-42d6-92c3-186fd1db9230.png" width="500" height="500"/>

It allows each container to have some portion of resources such as CPU, Memory, HD, Network Bandwidth. Control groups are there to decide how much resources each container will use. 

<img src ="https://user-images.githubusercontent.com/20486206/134533424-02cbac79-9bd1-4241-8ffd-04b7489690bf.png" width="500" height="500"/>

## What happens when a docker image is pulled?

<img src ="https://user-images.githubusercontent.com/20486206/134533670-66e0ea79-ca84-4d53-a143-37a684f949aa.png" width="500" height="500"/>

## What is docker image?

Docker image contains file system which contains all the dependencies and config files and run command which is used by the container to start a process

<img src ="https://user-images.githubusercontent.com/20486206/134534400-7f1e788c-2e78-4db0-92f7-1eb0bf04f861.png" width="500" height="500"/>

## What happens when docker container runs on system?

Docker container copies the file system from the docker image within the container and runs the runcommand to start the process.

<img src ="https://user-images.githubusercontent.com/20486206/134534843-de9a6fe2-7010-4972-b694-af6d5b2e95ee.png" width="500" height="500"/>

## What happens when you install docker in Windows or Mac OS?

Windows or Mac Os creates a linux virtual system which interacts with the guest os.

<img src ="https://user-images.githubusercontent.com/20486206/134535487-1ed6064f-b5ae-4c53-99ab-4b8e06906a17.png" width="500" height="500"/>

## What happens when a dockerfile is used to build a docker image?

Container pulls the base image and starts a temporary container based on that. Then it runs the command specified in the dockerfile. It takes the file system attached to that container and replace the new file system with the old one and tags the newly created image with a new name and delete the temporary container.
  
<img src ="https://user-images.githubusercontent.com/20486206/134543949-feece562-0abe-44ab-9594-e052bd8a3c92.png" width="500" height="500"/>


## A few docker commands

- Pull Image - docker pull <image_name>
- Docker create container - docker create <image_name>
- Docker start container - docker start <container_id>/ docker run <container_id>. The difference between start and run is that run prints the logs in the stdout by default. But start command will only print if a special option -a is passed.
- Docker replace start command - docker run <image_name> <runcommand>
- Docker run additional command - docker exec -it <container_id/name> <run_command>
- Docker logs - docker logs <container_id>
- Docker get command prompt - docker exec -it <container_id/name> sh
- Docker stop container - docker stop/kill <container_id/name> - docker kill triggers SIGKILL and stop triggers SIGTERM.
- Tag image during build - dokcer build -t <name(repo/image_name:version)> /path/to/folder
  

## Create docker image from container
  1. Start a container based on a base image.
  2. Install the specific software in that container
  3. commit the new filesystem of the running container as a new image -> docker commit -c <start command> <container_name>
  4. Start a new container with the newly created image.

## Port Mapping
  
  docker run -it <container_name> <host_port>:<container_port>
 
  <img src="https://user-images.githubusercontent.com/20486206/134553168-7935ef4f-dc19-4045-951e-4e344cb0b0ef.png" width="700" height="500"/>

## Workding Dir
  WORKDIR /usr/app
  
  
  
  
