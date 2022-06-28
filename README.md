# Docker DevOps with Node.js Express Mongodb

<h2>Codes for Ducker</h2>

- docker images : images list
- docker pull (image) : download image
- docker run (image) : run image and finish
- docker run -it(interactive terminal) (image) :  : run and continue
- docker run (image) sleep 3: up the image and wait 3 seconds
- docker ps(process) : it show us to which images up
- docker ps -a : all of the images history
- docker container ls: active container list
- docker container ls -a: all of the container history
- docker run --name (name flag) (image) : we named the container name
- docker start (name of image): up the container and execute at the background
- docker stop (name of image): it stops the execute
- exit : finish the application
- docker rm (container name/id): remove container
- docker container rm $(docker container ls -aq) : removes all container
- docker run (image):(version name) : download special version name
- docker image tag (image) (special image name) : we can rename the container
- docker run -d{depatch} (image name) : it execute at the background 
- docker attach (container id) : up the container which is depatched
- docker container logs (container id) : show us container logs
- docker inspect (container id) : show us everything about container
- docker rmi (imageName) : removes image
- docker network ls : network lists
- docker network rm (name/id) : network remove
- docker build . : building docker file
- docker build . -t (namingImage): naming image and building docker file
- docker container prune: deletes all of the containers
### Container Connection
- <h3>For mysql</h3>
  - docker run --name mysql-server -p OUTSIDE_PORT:INSIDE_POST -e(environment var) MYSQL_ROOT_PASSWORD=(PASSWORD) -d mysql
- <h3>For phpmyadmin</h3>
  - docker run --name pmyadmin -p OUTSIDE_PORT:INSIDE_POST <b>--link<b> mysql-server:db phpmyadmin/phpmyadmin

### Port MAPPİNG
- All of the container has ip (we can change it)
- Containers run in Docker Host
- if we want to access container at outside we need to use :
- docker run -p OUTSIDE_PORT:INSIDE_POST (container name)
### Volume Mapping 
- Container works like stateless thats mean that we can not save any information in it
- If we stop it we kill all of the information
- For that, we are using <b>Volume<b>
- Docker Engine hold it and if we stop the container all of the information can stay in Docker Host
- docker run -v /opt/data:/data/db (container name)
- docker run -v /opt/data:/data/db -p OUTSIDE_PORT:INSIDE_PORT (container name)
### Docker Network Types
- (Default) Bridge : Container links in gateway
- docker run (imageName) --network=none : We can not access at outside
- Host : docker run (imageName) --network=host : host has a ip we can access şn docker host
-  User Defined: docker network create --driver bridge subnet ..... --gateway ... (Name)
- docker run --name (imageNme) --net (networkName) -d (image) for database
- docker run --net (networkName) -p OUTSIDE_PORT:INSIDE_POST (imageName)
### Docker Compose
