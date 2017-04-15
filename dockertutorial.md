docker images

### docker ubuntu image
Pull image from hub
```
docker pull ubuntu
```
No 
```
apt-get install net-tools
``

### docker software component
docker console: interactive command line for run instructions
docker kitematic: list contain and online images


### Build your own image
tutorial
https://docs.docker.com/engine/getstarted/step_four/#step-1-write-a-dockerfile

way1
Write a dockerfile
```
FROM docker/whalesay:latest
RUN apt-get -y update && apt-get install -y fortunes
CMD /usr/games/fortune -a | cowsay
```
and build it 
```
docker build -t docker-whale .
```

way2
export a container 
see 'export a container as image and import back'
```
docker export <container-id> > xxx_image.tar
```

### export a container as image and import back

tutorial
https://blog.hinablue.me/docker-bi-jiao-save-export-dui-yu-ying-xiang-dang-cao-zuo-chai-yi/

Enter the interactive and 
```
docker run -t -i --name=hinaWeb ubuntu:latest bin/bash
```
after enter this container, install some software
```
root# apt-get update  
root# apt-get install software-properties-common python-software-properties  
```

exprot a exited container to a tar file
```
docker export hinaWeb > hinaWeb_Export.tar
```

Import the hinaWeb_Export.tar back as a images
you will see a local/hinaweb image
```
cat hinaWeb_Export.tar | docker import - local/hinaweb
docker images
```


### see containers
docker ps -a 

docker container list

### export container 
docker export <contain-id> > xxx.tar

### clean up all image

```
$ docker rm $(docker ps -a -q)
$ docker rmi $(docker images -a -q)
```




