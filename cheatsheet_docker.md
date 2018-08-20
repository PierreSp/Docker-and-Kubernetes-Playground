# Cheatsheet for docker 

## Links
- [Best tutorial site](http://container.training/)
- [Awesome docker](https://awesome-docker.netlify.com/)
- [Docker git](https://github.com/docker/labs)
- [Docker get started](https://docs.docker.com/get-started/)
- [Docker 101](https://github.com/docker/labs/tree/master/beginner)

## Display Docker info 
- ```docker info```                     # current version of docker
- ```docker version```                  # number of containers + status
- ```docker "container" --help```

## Execute and build Docker image
- ```docker build -t image .```         # Create image using this directory's Dockerfile
- ```docker run -p 4000:80 image```     # Run "image" mapping port 4000 (my machine) to 80 (inside docker)
- ```docker run -d -p 4000:80 image```  # Same imagename, but in detached (background) mode

## List Docker images and containers
- ```docker image ls ```                # List all images on this machine (-a also not running)
- ```docker ps```                      # List all running container
- ```docker container ls```             # List all running container (without pid)
- ```docker container ls --all```       # also shows not running containers
- ```docker container stop <hash>  ```  # Gracefully stop the specified container ($(docker container ls -a -q)  for all container)
- ```docker container kill <hash> ```   # Force shutdown of the specified container
- ```docker container rm <hash> ```     # Remove specified container from this machine
- ```docker container rm $(docker container ls -a -q) ```   # Remove all containers
- ```docker image rm <image id> ```    # Remove specified image from this machine
- ```docker image rm $(docker image ls -a -q) ``` # Remove all images from this machine

## Publishing docker images
- ```docker login ``` # Log in this CLI session using your Docker credentials
- ```docker tag <image> username/repository:tag ``` # Tag <image> for upload to registry
- ```docker push username/repository:tag ``` # Upload tagged image to registry
- ```docker run username/repository:tag ``` # Run image from a registry