'''# docker-learning
docker learning docs https://docs.docker.com/docker-for-mac/

This tells you about the command to pull docker images from docker hub and how to run those images on docker-containers 

#Explore the application.To check whether the docker installation was done properly 

root# 
root# docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
root# 

Start a Dockerized web server. Like the hello-world image above, if the image is not found locally, Docker pulls it from Docker Hub.

root# docker run --detach --publish=80:80 --name=webserver nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
f5d23c7fed46: Already exists 
918b255d86e5: Pull complete 
8c0120a6f561: Pull complete 
Digest: sha256:eb3320e2f9ca409b7c0aa71aea3cf7ce7d018f03a372564dbdb023646958770b
Status: Downloaded newer image for nginx:latest
f51e44b1a2007401d0d58c3d3370f6693f2fa85099a4824a237e99def76cb14e
root# 



#Docker version 

#Check docker versions 
root# docker --version
Docker version 18.09.2, build 6247962
root# 
root# 
root# docker-compose --version
docker-compose version 1.24.1, build 4667896
root# docker-machine --version 
docker-machine version 0.16.1, build cce350d7
root# 



# cat docker-compose.yml 
wordpress:
 image: wordpress
 links:
  - wordpress_db:mysql
 ports:
  - 8080:80
wordpress_db:
 image : mariadb
 environment:
  MYSQL_ROOT_PASSWORD: <put your own password>
phpmyadmin:
 image: corbinu/docker-phpmyadmin
 links:
  - wordpress_db:mysql
 ports:
  - 8181:80
 environment:
  MYSQL_USERNAME: root
  MYSQL_ROOT_PASSWORD: <put your own password>
# 
'''
