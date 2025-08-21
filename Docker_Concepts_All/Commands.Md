# All Commands used Daily:
====================================
Exercises: Docker HUB Account creation

docker installation:
curl -fsSL https://get.docker.com -o install-docker.sh
sh install-docker.sh

sudo docker info

sudo usermod -aG docker <user-name>
sudo usermod -aG docker ubuntu

docker container run -d -P nginx ===> Random Name Created

docker container run -p 32000:80 -d nginx          ====> Port- Forwarding
docker container run -P -d nginx                   ====> Random Port taken
docker container run -d -P --name --webappp1 nginx ====> Custome name

docker image ls
docker image ls -a
docker image ls -a

docker container ls
docker container ls -a          ===> hidden Conatiner 
docker container ls -a -q       ===> Commit Id

docker container rm -f $(docker container ls -a -q)
docker image rm -f $(docker image ls -a -q)

# Basic Container Commads:

docker exec -it nginx /bin/bash
pwd
Apllication - HTML
EDIT - use < Install>

docker container run --name apache -d -P httpd
docker container ls
docker container stop apache
docker container start apache
docker container rm apache

# To login into running container
docker container exec -it <name/id> /bin/bash

# creates the container and runs in the background
docker container run -d -P --name mycontainer httpd

# Dockefile Brife Discussion: 
