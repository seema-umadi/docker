# docker

1. what is docker
	docker is open source containerization platform. it enables developers to package application into containers.

2. how containers are different from virtual machines?
	VM is the entire copy of the operating system while the container will have minimal resources(less memory, less disk space, less usage of CPU) that are required to run a service.Virtualization lets you run multiple operating systems on the same physical server, whereas containerization enables you to deploy multiple applications or microservices on the same operating system without any hardware abstraction.

3. what is docker lifecycle
	user would create a dockerfile with a set of instructions or commands that defines a docker image. for example which base image to choose? what dependencies should be installed for the application to run. after that you need to build this image using docker build command. it converts your dockerfile to docker image. after that images is created and then user run the image using docker run command to create the container. and after that you can push the container in your dockerhub repository if you want.

4. what are docker components?
	1.Docker Daemon (dockerd): The Docker daemon runs on the host system and manages Docker objects such as images, containers, networks, and volumes. It listens for Docker API requests and performs tasks accordingly.
2.Docker Client (docker): The Docker client is the primary interface used by users to interact with Docker. Users can issue commands to the Docker daemon through the Docker client, such as building images, creating containers, and managing Docker resources.
3.Docker Images: Docker images are read-only templates used to create Docker containers. They contain everything needed to run an application, including the code, runtime, libraries, dependencies, and environment variables. Docker images are built from Dockerfiles using the docker build command and can be stored in Docker registries.
4.Docker Containers: Docker containers are lightweight, portable, and self-sufficient runtime environments that encapsulate an application and its dependencies. Containers are instances of Docker images that can be executed using the Docker Engine. Each container runs in isolation from other containers and the host system, but they can communicate with each other and with the host system through networking.
5.Docker Registry: Docker registries are repositories for Docker images. They store Docker images that can be shared publicly or privately within an organization. The Docker Hub is a popular public Docker registry, but organizations can also set up their private registries using Docker Registry or other compatible solutions.
6.Docker Compose: Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to use a YAML file to configure the services, networks, and volumes for your application, making it easier to manage complex Docker setups.
7.Docker Volumes: Docker volumes are persistent storage mechanisms used to store data generated or used by Docker containers. Volumes can be mounted into containers, allowing data to persist across container restarts and enabling data sharing between containers.

5. what is difference between docker copy and docker add?
	docker add can copy the files from a url unlike docker copy which can only copy files from host system into the container.

6. what is difference between CMD and entrypoint?
	cli arguments using docker run command will override the arguments specified using the cmd instruction.
	whereas entrypoint instruction in the shell form will override additional arguments provided using cli paraments or even through the cmd command.

7.what are the networking types in docker and what is the default?
	default networking is bridge. 1.bridge 2. overlay 3.host 4.macvian
1.bridge=the bridge is default network driver for a container which is used when multiple container communicate with the same docker host.
2.host= host will be used when user does not require any isolation between host and container
3.none = this driver will disable entire networking system.hindering any container from connecting with other containers.  
4.overlay=overlay is networking type where you can connect multiple host. its like a tunnel type networking.
5.macvlan= this network driver makes a container look like physical driver by assiging mac address and routing traffic between the containers through mac address

8.can you explain how to isolate networking between the containers?
	Docker provides a networking subsystem that allows you to create custom networks for your containers. By default, Docker containers connect to a bridge network named bridge, but you can create your own custom networks to isolate traffic between specific containers.After creating a custom network, you can attach containers to that network to isolate their networking. Containers connected to the same network can communicate with each other, while containers on different networks cannot.

	
9.what is multi stage build in docker?
	With multi-stage builds, you can define multiple build stages within the same Dockerfile. Each stage represents a phase of the build process, and you can copy artifacts or dependencies from one stage to another. This allows you to separate the build environment from the final runtime environment and discard unnecessary build dependencies, resulting in smaller and more efficient images.


10. what are distroless image?
	distroless images contain only your application and its runtime dependencies with a very minimum operating system libraries. they do not contain package managers, shells or any other programs you would expect to find in a standard linux distribution. they are very small and lightweighted images.
