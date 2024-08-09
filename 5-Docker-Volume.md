# Docker Volume
- Volume is simply a directory inside our container.
- Finally, we have to declare this directory as a volume and then share volume.
- Even if we stop the container still, we can access volume.
- Volume will be created in one container.
- You can declare a directory as a volume only while creating container.
- You can’t create volume from existing container.
- You can share one volume across any number of containers.
- Volume will not be included when you update an image.
- You can map volume in two ways:
  - a. Container to container
  - b. Host to container

## Benefits of Volume:
- Decoupling container from storage.
- Share volume among different containers.
- Attach volume to containers.
- On deleting container volume doesn’t delete.

## Creating Volume from Dockerfile:
Create a Dockerfile and write

> To see all volumne
```
docker volume ls
```

> To Create volumne

```
docker volume create image-volume
```

> To create container with volume

```
docker run -it -v image-volumne:/shared-volume --name my-container-01 ubuntu
```


```
FROM ubuntu
VOLUME “myvolume”
```

Then create image from this Dockerfile
```
#docker build -t myimage
```

Now create a container from this image and run
```
# docker run -it --name container1 myimage /bin/bash
```

Now do ls, you can see myvolume.


Now share volume with another container

> Container to container

```
# docker run -it --name container2 (new) --privileged=true –volumesfrom container1 ubuntu /bin/bash
```      

Now after creating container2, myvolume is visible. Whatever you do in one volume, can see from other volume.

```
#touch /myvolume/samplefile
```

```
#docker start container1
```

```
# docker attach container1
```

```
#ls/myvolume
```

You can see sample file here then exit.

Now create volume by using command:

```
#docker run -it --name container3 -v /volume2 ubuntu /bin/bash
```

```
# ls
```

```
#cd /volume2
```

Now create one file cont3file and exit

Now create one more container and share volume2
```
#docker run -it --name container4 --privileged=true --volumefrom container3 ubuntu /bin/bash
```

Now you re inside container do ls you can see volume2
Now create one file inside this volume and then check in container3 you can see that file.

### Volumes (Host to Container)
Verify files in /home/ec2-user

```
#docker run -it --name hostcontainer -v /home/ec2-user:/container --privileged=true ubuntu /bin/bash
```

```
#cd /container
```

Do ls, now you can see all files of host machine.

```
#touch contanerfile (in container) and exit
```

Now check in EC2 machine you can see this above file.

Some other commands:

```
#docker volume ls
```

```
#docker volume create <volumename>
```

```
#docker volume rm <volumename>
```

```
#docker volume prune (it removes all unused docker volume)
```

```
#docker volume inspect <volumename>
```

```
#docker container inspect <containername>
```
