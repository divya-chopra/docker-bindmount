# docker-bindmount

Docker Bind Mount: Bind mounts are way to mount the entire directory to the container's file system. The container treats the mounted directory as it's own directory.

Syntax: 

docker container run -v /path/on/host:/path/in/container

or

docker container run --mount type=bind, source=/data/mysql, target=/usr/share/nginx/html mysql

Use Case: To share an entire directory from the host with a docker container and keep up with any changes that are occurring inside this directory.
Bind Mount vs Docker Volume: Bind Mount directory can lie anywhere in the host but docker volumes help us persist data from anywhere on the container and persist it at /var/lib/docker/volumes

Case Scenario of this repo:

We are serving an app in the browser using an nginx server in the dev environment. 
Any changes that we are making to the files in the app directory should be reflected in the browser in real time.

As our nginx is running inside a container we will have to share the app directory with the nginx container as well.

Steps to follow: 

1. Clone this repo in local
2. Run container using nginx image, expose port 80, and mount the current directory to /usr/share/nginx/html 
Sample command: docker container run -d --name docker-conf -p 80:80 -v C:\Users\DC\Docker\volume-nginx\DockerConf:/usr/share/nginx/html nginx
3. Check local host at port 80 
4. Now we will modify index.html. Go to index.html in your repo and change London to India
5. Refresh your website and check if changes were made or not. 
6. You can inspect the docker container to check Mounts. 
