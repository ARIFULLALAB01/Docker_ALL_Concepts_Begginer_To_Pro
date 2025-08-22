# Docker Networking:
=====================================
 
**Docker networking allows containers to communicate with each other and host system.**
 1) **bridge networking**
 2) **Host networking** 
 3) **Overlay networking** 


## Networking Concepts:
=================================

1. **bridge networking: **Two scenarios**
Container one connects to container two,  Container one has isolation from container two. When you create a container. **Docker creates veth, That is docker0**. It allows docker container subnet to communicate with host. It is called bridge networking and it is default networking in docker. If there is no veth/docker0 the containerized application is not reachable from internet. So users will not be able to access application.
 **Other ways of networking in docker**

2. **Host networking** -  the container will directly use network of host, bind eth-network of your host.  Whoever has access to host have access to container. Least secure way of networking in docker.
3. **Overlay networking** -  when you need to create a network that is common in all the host of Kubernetes/swarm cluster.

**Scenarios Questions Challanges to Abhi from Students**
Q1: For suppose I have created a container with default bridge network or host network or custom network, but later stage I want to change the network to different one. Can I change without deleting the container?

Q2: Host is communicating with different containers with different networks. Can we make the same among the containers? What I mean is can only a container in the same host have multiple networks so that it will communicate with different containers?


# Lab Pratcise:
======================================

# Docker Networking:
=============

* Create a container with name Login and Logged into the container check the IP
  - docker run -d --name login nginx:latest
  - docker exec -it login /bin/bash
  - apt update
  - apt-get install iputils ping -y
  - apt-get install net-tools -y
  - ping -v
  
apt-get update
 apt-get install -y iputils-ping



* Create a container with name Logout and Logged into the container check the IP
 - docker ru -d --name logout nginx:latest
 - docker exec -it login /bin/bash
 - apt update
 - apt-get install iputils ping -y
 - apt-get install net-tools -y
 - ping -v

 - docker inspect login
 - docker inspect logout

 **tmux** usecase:
  ctrl+b "

  ctrl+b uparrow
  ctrl+b dwonarrow


**can i container access to Another Conatiner logged into login container access the ping the logout Container IP**


 - docker network ls
 - docker network rm test

* docker network create secure-network

 - docker run -d --name finance --network=secure-network  nginx:latest
 - docker exec -it login /bin/bash
 - docker exec -it logout /bin/bash
 - docker exec -it finance /bin/bash
     - ping to login container check the 


apt-get update
 apt-get install -y iputils-ping


## onemore Customer network: 
docker network create database-network
docker run -d --name database --network=database-network nginx:latest
apt-get update
 apt-get install -y iputils-ping

 ping - 172.17.0.2


 docker run -d --name Hari nginx:latest
 docker run -d --name arif nginx:latest
 docker run -d --name jhansi nginx:latest


* Finally check Default name of **Host_Network** Acess

  - docker run -d --name host-demo --network=host nginx:latest
  - docker ps
  - docker inspect host-demo 


**Example:**
arif -----> IPAddress": "172.17.0.5",
hari ----->  "IPAddress": "172.17.0.4",
login -----> "IPAddress": "172.17.0.2",
logout ---->   "IPAddress": "172.17.0.3"



finace --- > "IPAddress": "172.18.0.2",

databse --> ""IPAddress": "172.19.0.2",



