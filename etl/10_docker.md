## General Description
- Containers allow multiple applications to run on the same server, or (more specifically) operating instance
- Virtual Machines also achieve this, but tend to take up more space compared to containers
- Containers are lighter than VMs, since they don't include all of the unnecessary virtual hardware and drivers that VMs replicate
- We can think of the Dockerfile as the shopping list for ingredients, the image as our cake recipe, and the container as the cake we make

## Use-Cases of Containers
- Configuration made simple
	- Since containers represent lightweight instances of the host OS, we can create images with different system requirements or packages to provide different environments for similar application development
	- This can help developers avoid going through constant system setup and errors 
- Running multiple apps on a single servers
	- Since containers provide a high level of isolation, multiple applications can run on a single server
- Public cloud portability
	- Since containers represent lightweight instances of the host OS, they are portable enough to move across different server environments and run on different server environments
- Server Consolidation
	- Since containers can run multiple applications on a single server and are more lightweight than VMs, fewer servers can be used up than necessary (compared to VM and single server solutions)

## Comparison between VMs and Containers
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

## References
- https://www.reddit.com/r/docker/comments/982cag/docker_for_development_why_and_how/
- https://stackoverflow.com/questions/51693716/apache-hadoop-yarn-vs-kubernetes
- https://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-virtual-machine
- https://stackoverflow.com/questions/23735149/what-is-the-difference-between-a-docker-image-and-a-container
- https://www.rcrwireless.com/20170822/five-container-use-cases-tag27-tag99
