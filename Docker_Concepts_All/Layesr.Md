# Docker Layers Concepts: IMP (30/Jun/2025) - Class
===============================
Lets run the simple apline image with sleep 1d as cmd
  - docker pull alpine
  - docker image ls
  - docker run --name a1 -d alpine:latest sleep 1d
  - docker run --name a2 -d alpine:latest sleep 1d
 
 * Docker image is collection of readonly layers
 * Each docker container gets a writable layer for all changes done w.r.t storage and image layers are reused across containers
 * When we make any change in existing file which is part of image gets copied into writable layer and then modified (copy on write strategy)
 * When you delete the container writable layer is deleted.

 * How are layers getting created
 * Docker Image layers are create during image creation
 * Image automatically gets parent layers (FROM)
 * Any instruction that leads to change in storage will create a layer.
 * Having too many layers is not a good idea, layers are created for reusability.
 * On a broader note, the following instructions majorly lead to layer creation
   * RUN
   * ADD | COPY
 * Generally we club lots of commands in a RUN statement
  RUN apt update && \
    apt install openjdk-17-jdk -y && \
    .... \
    ... \
    ... \
