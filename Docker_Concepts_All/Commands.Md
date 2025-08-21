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

# Docker image Buit Command:

docker image build -t Spc:1.0 .

docker image build -t Spc:1.0 <Path location Give> (/tmp/hari/Dockerfile)

# To login into running container
docker container exec -it <name/id> /bin/bash

# creates the container and runs in the background
docker container run -d -P --name mycontainer httpd

# Dockefile Brife Discussion: 
 ** we are USiung the **[text](SpringPerclinc.Md)** each and evrything from thise File Explained

# Docker image Push Command:

docker login
 - authentication:
    - username & Password
docker tag <local-image-name>:<tag> arifulla/myapp:<tag>
docker tag spc:latest arifullalab01/springboot:1.0
docker push arifullalab01/springboot:1.0


# Docker image Push To ECR:

docker login
 - authentication:
    - AWSCli -- Install
    - Role - EC2 administartor (IAM - Role -)Attahced
    - ECR-Registry > push Commands ==>  we follow the the heirachy





