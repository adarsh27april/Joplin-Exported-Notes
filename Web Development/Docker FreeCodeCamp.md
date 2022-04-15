```bash
sudo docker version
```

[for downloading the image of the whalesay application](https://hub.docker.com/r/docker/whalesay)

then run command:

```bash
sudo docker run docker/whalesay cowsay Hello-World
```

![fd37fb6e4035c86f14279d3ab60c30ae.png](../_resources/fd37fb6e4035c86f14279d3ab60c30ae.png)

![fe74f49d397b0c5f417209ccdc33606c.png](../_resources/fe74f49d397b0c5f417209ccdc33606c.png)

`docker run  <name of image>` will run the image & if image isn't present then it download it from the dockerhub.


`docker ps` command will list all running containers and some basic things about them

`docker ps -a` will show all running, previously running & exited containers.

`docker stop  <name of container>` to stop the running container 

`docker rm  <name of container>` to remove a stopped or exited container, note that although the container is removed the image is still present.

`docker images` shows all the images present in the system

1. ![35bec7374728e85d521272a9a522f99d.png](../_resources/35bec7374728e85d521272a9a522f99d.png)

2. note on running the command `docker run  <name of image>` a new container of the image will be created with some different container name and then it will run.
![6d1cd0084975663f2b088e32903d8dea.png](../_resources/6d1cd0084975663f2b088e32903d8dea.png)

to remove an image: 1st ensure no containers of the image are running, and delete all related containers.

`docker rmi <name of image>` 

`docker pull <name of image>` will only pull the image and not run it in a container
