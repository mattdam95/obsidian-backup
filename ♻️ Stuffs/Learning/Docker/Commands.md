
### Manage containers

*Show a list of runnings containers*
`docker PS
*Show a list of all containers*
`docker ps —a
*Delete a container*
docker rm CONTAINER
`docker rm web
*Delete a runt-ung container*
`docker rn -t CONTAINER
`docker rm —f web
*Delete stopped containers*
`docker container prune
*Stop a running container*
`docker stop CONTAINER
`docker stop web
*Start a stopped container*
`docker start CONTAINER
`docker start web
*Copy a file from a container to the host*
`docker cp CONTAINER: SOURCE TARGET
`docker cp web:/index.html index.html
*Copy a file from the host to a container*
`docker cp TARGET CONTAINER:SOURCE
`docker cp index. html web:/index.html
*Start a shell Inside a running container*
`docker exec -it CONTAINER EXECUTABLE
`docker exec —it web bash
*Rename a container*
`docker rename OLD_NAME NEV_NAME
`docker rename 096 web
*Create an image out Of container*
`docker commit CONTAINER
`docker web

### Manage images
*Download an image*
`docker pull IMAGE:[TAG]
`docker pull nginx
*Upload image to a repository*
`docker push IMAGE
`docker push myinage:1.0
*Delete an Image*
`docker rmi MAGE
*Show a list of all Images*
`docker images
*Delete dangling images*
`docker images prune
*Delete all unused images*
`docker images prune —a
*Build an image fronn a Dockerflle*
`docker build DIRECTORY
`docker build .
*Tag an Image*
`docker tag IMAGE NEWIMAGE
`docker tag ubuntu ubuntu: 18.04
*Budd and tag an image from a Dockerflle*
`docker build -t IMAGE DIRECTORY
`docker build —t myimage .
*Save an image to tar file*
`docker save IMAGE > FILE
`docker save nginx > nginx. tar
*Load an image for a .tar file*
`docker load -i TARFILE
`docker load —i nginx. tar`



![[Pasted image 20230106121331.png]]