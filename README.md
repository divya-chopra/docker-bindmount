# docker-bindmount

Docker Bind Mount: Bind mounts are way to mount the entire directory to the container's file system. The container treats the mounted directory as it's own directory.

Syntax: 

docker container run -v /path/on/host:/path/in/container

Use Case: To share an entire directory from the host with a docker container and keep up with any changes that are occurring inside this directory.
Bind Mount vs Docker Volume: Bind Mount directory can lie anywhere in the host but docker volumes help us persist data from anywhere on the container and persist it at /var/lib/docker/volumes

Case Scenario of this repo:

We are serving an app in the browser using an nginx server in the dev environment. 
Any changes that we are making to the files in the app directory should be reflected in the browser in real time.

As our nginx is running inside a container we will have to share the app directory with the nginx container as well.

Steps to follow: 

