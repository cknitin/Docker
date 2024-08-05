# Install Docker
```
yum install docker -Y

apt install docker -Y

sudo docker -v

```

# Basic Docker Commands:

- To see all images present in your local repo:
```
# docker images
```

- To find out images in docker hub
```
# docker search image_name
```

- To download image from dockerhub to local machine
```
# docker pull image_name
```

- To give a name to container
```
# docker run -it --name new_name image_name /bin/bash
```

- To check service start or not (status)
```
# docker service status

Ubuntu
sudo systemctl status docker
```

- To start:
```
#docker service start

Ubuntu
sudo systemctl start docker
```

- To stop: 
```
# docker service stop

Ubuntu
sudo systemctl stop docker
```

- To start container
```
#docker start container_name
```

- To go inside container
```
# docker attach container_name
```

- To see all containers
```
# docker ps -a
```

- To see running containers
```
# docker ps
```

- To stop container
```
# docker stop container_name
```

- To delete a container
```
# docker rm container_name
```

- Create container from our own Image:
Login into AWS account and start your EC2 instance, access it from putty.
Now we have to create container from our own image. Therefore, create one container first:

```
#docker run -it –name container_name image_name /bin/bash
```

```
#cd tmp/
```

Now create one file inside this tmp directory
```
# touch myfile
```

Now if you want to see the difference between the basic image and the changes on it
```
# docker diff container_name image_name
```

Now create image of this container
```
# docker commit newcontainer_name image_name
```

```
#docker images
```

Now create container from this image
```
# docker run -it --name newcontanier_name image_name /bin/bash
```

```
# ls 
```

```
# cd tmp
```

```
# ls (you will get all of your files)
```
