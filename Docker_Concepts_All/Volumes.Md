# Docker Volume Concepts: Explained:
======================
# Volume use cases:
 
1) Bind mounts  --> /app -- Folder 
2) Volumes  -- > Comes From Disk

## Problems:

*  Containers are Ephemeral means Short-Leaved

1. Previous Logs for Auditing
2. Frontend vs Backend - logs are UpToDate so loges create Dynamically
3. Read Some file from Logs and Means (User application logs pushed to Files Every times)

========>

docker volume -v
docker volume --mount  ==> Verbos

docker volume ls
docker volume create CSSarif
docker volume inspect CSSarif
docker volume rm CSSarif
clear

docker volume ls
docker images | head -5

vim Dockerfile
docker build .
docker build -t volumedemo Dockerfile
docker run -d --mount source=arif target=/app nginx:latest

docker build -t CSSarif Dockerfile

vim Dockerfile

FROM ubuntu


docker ps
docker inspect <name-Of-Container>
==>
If u want to add more information like if u want to read/or/Write/or/ Any modification just use the ",(Comma)" Symbol

docker run -d --mount source=arif target=/app nginx:latest

docker volume rm arifVolume ==
1st stop the container then only we can delete the Volume



