# Docker Port Expose

Login into AWS account, create one linux instance.

Now go to putty -> login as -> ec2-user

```
#sudo su
```

```
# yum update -y
```

```
# yum install docker -y
```

```
# service docker start
```

```
# docker run -td --name techserver -p 80:80 ubuntu
```

```
# docker ps
```

```
# docker port techserver o/p- 80/tcp – 0.0.0.0/80
```

```
# docker exec -it techserver /bin/bash
```

```
# apt-get update
```

```
# apt-get install apache2 -y
```

```
# cd /var/www/html
```

```
# echo “write some msg” > index.html
```

```
# service apache2 start
```

```
# docker run -td --name myjenkins -p 8080:8080 jenkins
```


## Difference between docker attach and docker exec:
- Docker ‘exec’ creates a new process in the container’s environment while docker ‘attach’ just connect the standard input/output of the main process inside the container to corresponding standard input/output error of current terminal.
- Docker ‘exec’ is specifically for running new things in an already started container be it a shell or some other process.

### What is the difference between docker expose and publish:
Basically you have three options:

- 1. Neither specify expose nor -p
- 2. Only specify expose
- 3. Specify expose and -p


1. If you specify neither expose nor -p, the service in the container will only be accessible from inside the container itself.
2. If you expose a port, the service in the container is not accessible from outside docker but from inside other docker containers so this is good for inter-container communication.
3. If you expose and -p a port, the service in the container is accessible from anywhere even outside docker

If you do –p but do not expose docker does an implicit expose. This is because if a port is open to
the public, it is automatically also open to the other docker containers. Hence -p includes expose.
