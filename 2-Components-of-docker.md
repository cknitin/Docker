# Components of Docker:

## A. Docker Daemon:
- Docker daemon runs on host O.S.
- It is responsible for running containers to manages docker services.
- Docker daemon can communicate with other daemons.

## B. Docker Client:
- Docker users can interact with docker through a client.
- Docker client uses commands and REST API to communicate with the docker
daemon.
- When a client runs any server command on the docker client terminal, the client
terminal sends these docker commands to the docker daemon.
- It is possible for docker client to communicate with more than one daemon.

## C. Docker Host:
- Docker host is used to provide an environment to execute and run applications.
- It contains the docker daemon, images, containers, networks and storages.

## D. Docker Hub/ Registry:
- Docker registry manages and stores the docker image.
- There are two types of registries in the docker:
  - a. Public Registry: it is also called as docker hub.
  - b. Private Registry: it is used to share image with in the enterprise.

## E. Docker Image:
- Docker images are the read only binary templates used to create docker containers.
or
- Single file with all the dependencies and configuration required to run a program.
Ways to Create an Image:

  -  a. Take image from the docker hub.
  -  b. Create image from docker file.
  -  c. Create image from existing docker containers.

## F. Docker Containers:
- Containers hold the entire packages that is needed to run the application.
  Or
- In other words, we can say that the image is a template and the container is a copy
  if that template.
- Container is like a virtual machine.
- Images becomes container when they run on docker engine.

