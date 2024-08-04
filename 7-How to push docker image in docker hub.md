# How to push docker image in docker hub:

- Go to AWS account – select Amazon linux

- Now go to putty – login as – ec2-user

```
#sudo su
```

```
#yum update -y
```

```
#yum install docker -y
```

```
#service docker start
```

```
#docker run -it ubuntu /bin/bash
```

Now create some files inside container, now create image of this container

```
#docker commit container1 image1
```

Now create account in hub.docker.com

Now go to EC2 instance

```
#docker login
```

Enter your username and password

Now give tag to your image

```
#docker tag image1 dockerid/newimage
```

```
#docker push dockerid/newimage
```

Now you can see this image in docker hub account
Now create one instance in another region and pill image from hub

```
#docker pull dockerid/newimage
```
#docker run -it --name mycon dockerid/newimage /bin/bash
