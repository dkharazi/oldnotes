## General Description
- Containers allow multiple applications to run on the same server, or (more specifically) operating instance
- Virtual Machines also achieve this, but tend to take up more space compared to containers
- Containers are lighter than VMs, since they don't include all of the unnecessary virtual hardware and drivers that VMs replicate
- We can think of the Dockerfile as the shopping list for ingredients, the image as our cake recipe, and the container as the cake we make

## Use-Cases of Containers
- Automated configuration
	- Since containers represent lightweight instances of the host OS, we can create images with different system requirements or packages to provide different environments for similar application development
	- This can help developers avoid going through constant system setup and errors 
- Running many different apps on a single server
	- Since containers provide a high level of isolation, multiple applications can run on a single server
- Portable over the cloud
	- Since containers represent lightweight instances of the host OS, they are portable enough to move across server environments and run on different server environments
- Server consolidation due to lightweight nature
	- Since containers can run multiple applications on a single server and are more lightweight than VMs, fewer servers can be used up than necessary (compared to VM and single server solutions)
- Fault tolerant
	- If one container completely blows up in our face (i.e. interrupted or failure), then our other containers running on that same system will be fine

## Comparison between VMs and Containers
- Roughly, a virtual machine is an emulation of a physical computer
- On the other hand, a container is an emulation of an operating system
- In other words, a virtual machine emulates the physical hardware, which is why we can run any operating system on top of any other (and also why drivers are included), whereas a container emulates the operating system
- Container
	- Lightweight
	- Native Performance
	- All containers share the host OS
	- OS virtualization
	- Startup time in milliseconds
	- Requires less memory space
	- Process-level isolation, so possibly less secure
- VMs
	- Heavyweight
	- Limited Performance
	- Each VM runs in its own OS
	- Hardware-level virtualization
	- Startup time in minutes
	- Allocates required memory
	- Fully isolated and hence more secure

## Dockerfile
- A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image
- Using docker build, users can create an automated build that executes several command-line instructions in succession
- For example, we could specify a python version to be built, files to be included in a directory, etc.

## Image
- Given a Dockerfile, the Docker engine builds an image
- An image represents a snapshot of a container
- We can think of an image as a template that can be turned into a container
- Or we can think of an image as a "soft-build" of a container without the resources being allocated to it

## Container
- Given an image, the Docker engine runs a container
- A container represents an instance of an image
- A container is created by the Docker engine taking in an image, adding a read-write filesystem on top, and initializing various settings (i.e. network ports, container name, container ID, resource limits, etc.)

## Caching Images
- Once an image is built on a machine, the image will be cached in Docker (i.e. /var/lib/docker)
- As a result, we won't need to rebuild the image every time we run a container if changes haven't been made to an image
- If any changes have been made to an image, Docker will rebuild the image
- Fortunately, the process of rebuilding an image won't take as long, since Docker will only process the code changed in the Dockerfile
- Docker will not process the unchanged code in the Dockerfile because building that part of the image would be redundant, since it is cached

## Mounting Host Directories to Containers
- Docker allows you to mount host directories (or volumes) when running containers
- Mounting host directories to containers differs from copying host directories to containers
- Specifically, any changes made to a mounted host directory in a container will carry over to the host directory as well
- On the other hand, any changes made to a copied host directory in a container will not carry over to the host directory
- In other words, volumes are the preferred mechanism for persisting data generated by and used by Docker containers
- Host directories are copied when building our image, whereas host directories are mounted when running our container
- We can mount volumes to a container by using the v flag when running our container
	- For example, -v [host_dir:container_dir]
- We can copy host directories to a container by using the COPY command when building our image
	- For example, COPY [host_dir]

## References
- https://insights.sei.cmu.edu/sei_blog/2017/09/virtualization-via-containers.html
- https://www.reddit.com/r/docker/comments/982cag/docker_for_development_why_and_how/
- https://stackoverflow.com/questions/51693716/apache-hadoop-yarn-vs-kubernetes
- https://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-virtual-machine
- https://stackoverflow.com/questions/23735149/what-is-the-difference-between-a-docker-image-and-a-container
- https://www.rcrwireless.com/20170822/five-container-use-cases-tag27-tag99
- https://docs.docker.com/storage/volumes/
