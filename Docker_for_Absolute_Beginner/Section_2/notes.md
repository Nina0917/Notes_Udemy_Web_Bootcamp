## Basic Docker Commands

docker run ngix

- pull the image ngixand run the container

docker ps

- show all the running container

docker ps -a

- show all containers.

docker stop container_name

- stop a container

docker rm container_name

- remove a container

docker rmi image_name

- delete an image
- make sure no container is running on the image before you remove it

<br>

docker pull ngix

- pull the image of ngix but don't run the container

What happens if you execute "docker run ubuntu" ?

- the contaienr exits immediately because docker is supposed to run an application. However, ubuntu is a operating system. There is no process or application running in it by default.

docker exec container_name cat /etc/hosts

- when the container is running, see content of the file within /etc/hosts

<br>

docker run -d application_name

- run the container in the background
- 'd' means detach

<br>

## Demo - Docker Commands

docker run centos

- pull and download the image centos
- since we don't ask it to do anything, it exits immediately

<br>

docker run -it centos bash

- Now we run the centos container again as well as the bash command
- '-it' automatically log me in to the container

<br>

cat /etc/_release_

- check the operating system I am on
- the result is NAME="CentOS Linux VERSION="8"

<br>

exit

- exit centos container

<br>

docker ps

- no results because I don't have a running container right now

<br>

docker run -d centos sleep 20

- run centos container again with '-d' option, so I can go back to terminal
- it only keeps alive for 20 seconds

<br>

docker ps

- it shows the container we just started

<br>

docker run -d centos sleep 2000

docker stop container_name/container_id

docker rm conatiner_name/id

- run the centos container and keep it alive for 2000 seconds
- stop the container (but it still stays on the disk space)
- clear up containers

<br>

docker images

- show all existing images

<br>

docker rmi image_name

- remove images
