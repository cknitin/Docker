# Dockerfile
Dockerfile is basically a text file. It contains some set of instructions. Automation of docker image
creation.

## Dockerfile components:

- FROM: for base image, this command must be on the top of the dockerfile.
- RUN: to execute commands, it will create a layer in image
- MAINTAINER: author/ owner/ description
- COPY: copy files from local system (docker vm) we need to provide source, destination (we can’t
  download file from internet and any remote repo.)
- ADD: similar to copy but it provides a feature to download files from internet, also extract file at docker image side.
- EXPOSE: to expose ports such as port 8080 for tomcat , port 80 for nginx etc.
- CMD: execute commands but during container creation.
- ENTRYPOINT: similar to CMD but has higher priority over CMD, first commands will be executed by ENTRYPOIN only.
- ENV: environment variables


### Dockerfile

- Create a file named Dockerfile
- Add instructions in Dockerfile
- Build dockerfile to create image
- Run image to create container

```
# vi Dockerfile
```

FROM ubuntu
```
RUN echo “Nagarjuna hota” > /tmp/testfile
```

To create image out of Dockerfile
```
# docker build -t myfile
#docker ps -a
```

### docker image
Now create container from the above image
```
#docker run -it --name mycon mying /bin/bash
```

```
#cat /tmp/testfile
```

```
#vi dockerfile
```

FROM ubuntu
```
WORKDIR /tmp
RUN echo “thank you” > /tmp/testfile
ENV myname naga
COPY testfile1 /tmp
ADD test.tar.gz /tmp
```
