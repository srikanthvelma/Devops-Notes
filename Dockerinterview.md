Docker Interview Questions and Answers
--------------------------------------
1. What is Docker?
```
Docker is containerization platform that is used for building,deploying and running applications.
it is used to automate the deployment the applications, using lightweight ,portable containers
```
2. Explain Docker Images?
* A Docker image is a read-only template that contains a set of instructions for creating a container that can run on the Docker platform
* Docker will be created by docker file by using base image
* A Docker image is made up of a collection of files that bundle together all the essentials – such as installations, application code, and dependencies – required to configure a fully operational container environment
*  Docker images have intermediate layers that increase reusability, decrease disk usage, and speed up docker build by allowing each step to be cached
3. What are different ways of building docker images?
* we can create docker images by 2 ways:
  * Interactive: By running a container from an existing Docker image, manually changing that container environment through a series of live steps, and saving the resulting state as a new image.
  * Dockerfile: By constructing a plain-text file, known as a Dockerfile, which provides the specifications for creating a Docker image.
4. what is Dockerfile?
*  A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image
*  Docker can build images automatically by reading the instructions from a Dockerfile
*  In Dockerfile we will use a base Image called as scratch which has nothing in it, from there we can write all our commands in the form of instructions by using diffrent directives of dockerfile
*  Instructions/directives are
   *  FROM
   *  LABEL
   *  ADD
   *  COPY
   *  RUN
   *  EXPOSE
   *  CMD
   *  ENTRYPOINT
   *  VOLUME
   *  USER
   *  WORK_DIR
   *  ENV
   *  ARGS
5. How can Container different than VM?
* VM virtualizes entire hardware layer and build with guset os on top of host os
* Container only virtualizes software layers above os level and uses host os and hardware
    * container is light weight and portal and can run on cross platform like ios ,andriod and can run on any cloud env and it can resuable by using docker images
    * as it is light weight ,uses less space and so it can applications with more speed
6. Can you tell about namespaces and how they are used in docker?
* Namespaces are one of a feature in the Linux Kernel
* namespaces provide a layer of isolation.
*  Docker uses namespaces of various kinds to provide the isolation that containers need in order to remain portable
*  Each aspect of a container runs in a separate namespace and its access is limited to that namespace
*  Namespace Types:
   *  Procees ID
   *  Mount
   *  User
   *  Network
* USER is a improtant namespace as running container with root is not that secure
* so to avoid this we can run inte namespace of user
7. What is diff between COPY and ADD
8. layers concept in docker
9. Expose and Volume
* The VOLUME instruction creates a mount point with the specified name 
10. Docker workflow for CI/CD
