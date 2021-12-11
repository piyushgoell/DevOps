# **LifeCycle and Maintenance**

## **Launching and Listing Container**

    # list the running container
    docker container ls
    docker container ls -a [list all container including one in stopped state]

    # Run a container
    docker run <image>

    # Run container and drop to shell
    docker run -it <image>
    docker run --interactive --tty <image>

    # Run container in background
    docker run -d <image>

    # Container restart settings
    docker run --restart (always|no|on-failure[:maxretries]|unless-stopped) <image>

    # Remove container when exited
    docker run -rm <image>

    # Provide container nickname
    docker run --name <name> <image>

    example:-
    docker run -dt --restart always --name mycontainer alpine
    docker run -it --name rm-test -rm alpine [automatically remove container once done]

## **Accessing the container**

    # Start a container
    docker start <container>

    # Run a command against a container
    docker exec <container> <command>

    # Drop into a shell
    docker exec -it <container> <shell>

    # Copy file to container/ Copy container file to localhost

    docker cp <source> <container>:<destination>
    docker cp <container>:<source> <destination>

    example:-

    docker exec test apk add nginx

    docker exec -it test ash

## **Container Management**

    # Stop and restart container
    docker stop <container>
    docker restart <container>

    # remove a container
    docker rm <container>

    # Remove all stopped containers
    docker  container prune

    # Rename a container
    docker rename test test1

    # View container metrics
    docker stats [<container>]

## **Publishing the Container**

    # View container information
    docker inspect <container>

    # Create a container image
    docker commit <container> <name>

    # Map container port to host server
    docker run -p <host_port>:<container_port> <container>

    example:-

    cloud_user@dockerhost:~$ ls webfiles/
        default.conf  html
        cloud_user@dockerhost:~$ cat webfiles/default.conf
        server {
                listen 80 default_server;
                listen [::]:80 default_server;

                root /var/www/html/;
        }
        
    cloud_user@dockerhost:~$ docker exec web mkdir /var/www
    
    cloud_user@dockerhost:~$ docker cp webfiles/default.conf web:/etc/nginx/conf.d/default.conf
    
    cloud_user@dockerhost:~$ docker cp webfiles/html/ web:/var/www/
    
    cloud_user@dockerhost:~$ docker exec web ls /var/www/html
    LICENSE assets css index.html js

    cloud_user@dockerhost:~$ docker exec web chown -R nginx:nginx /var/www/html
    
    cloud_user@dockerhost:~$ docker exec web nginx -s reload

    cloud_user@dockerhost:~$ docker inspect web | grep IP

    cloud_user@dockerhost:~$ curl 172.17.0.2

    cloud_user@dockerhost:~$ docker commit web web-image

    cloud_user@dockerhost:~$ docker run -dt --name web01 -p 80:80 web-image

    cloud_user@dockerhost:~$ curl localhost

## **Images**

1. Comprised of layers ->
2. Layers are cached ->
3. Everything we need ->
4. Base images on other images -> Images can have a parent image on which they are based. there is no need to recreate the wheel each time.

## **Building a D ockerfile**

1. Defime parent image

    Use the **FROM** instruction to set the parent image to the **node:18-alpine** Node.JS 10 Alpine image.

2. Create directory structure
   
   Use **RUN** to create the **/home/node/app/node_modules** directory and set **node** as the owner/group.

3. Move directories

    Use **WORKDIR** to set **/home/node/app** as the active directory.

4. Copy files

    Use **COPY** to move the **package*.json** metadata files to the working directory.

5. Configure the npm registry

    Use **RUN** to set the **npm** registry via the **npm config set registory** command.

6. Install required packages

    Use **RUN** to have **npm** install any prerequisite packages for our application.

7. Copy more files

    Use **COPY** to copy the remaing files from the dockerfile's working directory.

8. Switch users

    Use **USER** to switch to the **node** user.

9. Expose port

    Use **EXPOSE** to ensure we can access the application on container port 8080.

10. Run the application
    
    Use **CMD** to run the node executable against the **index.js** file

#### **Wrap Up**
        # Provide a parent/scratch image
        FROM <image|scratch>

        # Run a command against the default shell
        RUN <command>

        # Set the working directory
        WORKDIR <directory/path>

        # COPY files
        COPY --chown <user> <source> <destination>

        # Copy files (can be from url)
        ADD <source> <destination>

        # Switch to user
        USER <user>

        # Expose a port
        EXPOSE <port>

        # Single command to eun when container starts
        CMD ["<executable>","<pram1>", "<pram2>"]

## **Image Management**

    # Save an image locally
    docker pull <image>

    # List available images
    docker image ls

    # Remove images
    docker image rm <image>

    # Prune all unused images
    docker image prune -a

    # View image information
    docker image inspect <image>

## Using Docker Hub

    # Log in to the Docker Hub
    docker login --username=<username>
    ex: docker login --username=piyush

    # Tag image for a repository
    docker tag <image> <username>/<repo>:<version>
    ex: docker tag appimage piyush/demo-app:latest

    # Push to repo
    docker push <username>/<repo>
    ex: docker push piyush/demo-app 

    # Log out of Docker Hub 
    docker

## Hands On

    FROM alpine:3.13
    RUN apk upgrade
    RUN apk add nginx
    COPY containerhub/files/default.conf /etc/nginx/conf.d/default.conf
    RUN mkdir -p /var/www/html/
    WORKDIR /var/www/html
    COPY --chown=nginx:nginx containerhub/files/html/ .
    EXPOSE 80
    # To set the processid
    CMD ["nginx","-g","pid /tmp/nginx.pid; daemon off;"]

