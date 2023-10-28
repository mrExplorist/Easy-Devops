# Docker README

## Introduction

Welcome to the Docker README! Docker is an open-source containerization platform that simplifies the process of developing, shipping, and running applications. In this extensive guide, we will delve into Docker's features, uses, and best practices to help you become proficient with containerization.

## Table of Contents

- [Docker README](#docker-readme)
  - [Introduction](#introduction)
  - [Table of Contents](#table-of-contents)
  - [What is Docker?](#what-is-docker)
  - [Why Use Docker?](#why-use-docker)
  - [Docker Installation](#docker-installation)
  - [Docker Basics](#docker-basics)
    - [Containers](#containers)
    - [Images](#images)
    - [Dockerfile](#dockerfile)
    - [Docker Hub](#docker-hub)
  - [Running Containers](#running-containers)
    - [Container Lifecycle](#container-lifecycle)
    - [Container States](#container-states)
  - [Managing Containers](#managing-containers)
    - [Starting and Stopping Containers (continued)](#starting-and-stopping-containers-continued)
    - [Viewing Container Logs](#viewing-container-logs)
    - [Interacting with Containers](#interacting-with-containers)
    - [Removing Containers](#removing-containers)
  - [Docker Compose](#docker-compose)
    - [Creating a Docker Compose File](#creating-a-docker-compose-file)
  - [Docker Compose Example](#docker-compose-example)
    - [Running Docker Compose](#running-docker-compose)
  - [Docker Networking](#docker-networking)
    - [Docker Bridge Network](#docker-bridge-network)
    - [Custom Networks](#custom-networks)
    - [Container Communication](#container-communication)
  - [Docker Volumes](#docker-volumes)
    - [Data Persistence](#data-persistence)
    - [Volume Types](#volume-types)
  - [Docker Swarm](#docker-swarm)
    - [Swarm Mode](#swarm-mode)
    - [Service Deployment](#service-deployment)
    - [Scaling Services](#scaling-services)
  - [Docker Security](#docker-security)
    - [Image Security](#image-security)
    - [Container Isolation](#container-isolation)
    - [Secure Configuration](#secure-configuration)
  - [Docker Best Practices](#docker-best-practices)
    - [Image Management](#image-management)
    - [Container Orchestration](#container-orchestration)
    - [System Optimization](#system-optimization)
  - [Troubleshooting](#troubleshooting)
    - [Container Crashes](#container-crashes)
    - [Networking Issues](#networking-issues)
    - [Resource Constraints](#resource-constraints)
  - [Docker Ecosystem](#docker-ecosystem)
    - [Kubernetes and Docker](#kubernetes-and-docker)
    - [CI/CD with Docker](#cicd-with-docker)
    - [Monitoring Docker](#monitoring-docker)
  - [Summarizing Commands](#summarizing-commands)
    - [Docker Basic](#docker-basic)
    - [Docker Container](#docker-container)
    - [Docker Network](#docker-network)
    - [Docker Images](#docker-images)
    - [Docker Volume](#docker-volume)
    - [Docker Compose](#docker-compose-1)
    - [Docker Swarm and Services](#docker-swarm-and-services)
    - [Docker Stack](#docker-stack)
    - [Tips and Short hands](#tips-and-short-hands)
  - [Conclusion](#conclusion)

11. [**Docker Security**](#docker-security)

- [Image Security](#image-security)
- [Container Isolation](#container-isolation)
- [Secure Configuration](#secure-configuration)

12. [**Docker Best Practices**](#docker-best-practices)

- [Image Management](#image-management)
- [Container Orchestration](#container-orchestration)
- [System Optimization](#system-optimization)

13. [**Troubleshooting**](#troubleshooting)

- [Container Crashes](#container-crashes)
- [Networking Issues](#networking-issues)
- [Resource Constraints](#resource-constraints)

14. [**Docker Ecosystem**](#docker-ecosystem)

- [Kubernetes and Docker](#kubernetes-and-docker)
- [CI/CD with Docker](#ci-cd-with-docker)
- [Monitoring Docker](#monitoring-docker)

15. [**Conclusion**](#conclusion)

## What is Docker?

Docker is an open-source platform designed to simplify the process of developing, shipping, and running applications. It employs containerization technology, allowing you to package applications and their dependencies into a single, isolated unit called a container. Containers ensure that an application behaves consistently across different environments.

## Why Use Docker?

**1\. Consistency**: Docker ensures that applications run consistently across development, testing, and production environments.

**2\. Isolation**: Containers isolate applications and their dependencies, preventing conflicts and ensuring security.

**3\. Portability**: Containers can run on any system with Docker, making it easy to move applications across different environments.

**4\. Efficiency**: Docker containers are lightweight and start quickly, saving resources and reducing overhead.

**5\. Scalability**: Docker can easily scale applications by spinning up multiple containers, making it ideal for microservices architectures.

## Docker Installation

Before diving into Docker, you need to install it on your system. Docker provides installers for various operating systems, including Windows, macOS, and Linux. Follow the installation instructions for your specific platform, and ensure that you have Docker Desktop (on Windows and macOS) or Docker Engine (on Linux) up and running.

## Docker Basics

### Containers

Containers are the core building blocks of Docker. They are lightweight, standalone, and executable packages that include everything required to run an application, such as code, runtime, libraries, and dependencies. Containers share the host operating system's kernel, which makes them efficient and easy to deploy.

Containers are ideal for running applications in an isolated and reproducible environment.

### Images

Docker images are read-only templates used to create containers. An image includes the application code, libraries, and dependencies. Think of an image as a snapshot of a container that can be run on any system with Docker installed.

You can find images on Docker Hub, a public registry that hosts thousands of pre-built Docker images. Docker Hub is a valuable resource for finding and sharing images.

### Dockerfile

A Dockerfile is a text file that defines the instructions for building a Docker image. It specifies the base image, application code, and configuration settings. Dockerfiles are used to automate image creation, ensuring that you can reproduce your application's environment consistently.

Creating a Dockerfile is a crucial step in building custom images for your applications.

### Docker Hub

Docker Hub is a repository of Docker images where you can find, share, and collaborate on images. It offers a vast collection of images for various applications, programming languages, and frameworks. Docker Hub simplifies the process of distributing and deploying software.

## Running Containers

Running a container is a straightforward process. You specify the image to use and any runtime options. Docker takes care of setting up the isolated environment and running the application. Here's a basic example:

```
docker run -d -p 80:8080 my-web-app
```

In this command, we're running a container in detached mode, mapping port 80 on the host to port 8080 in the container, and using the "my-web-app" image.

### Container Lifecycle

Containers have a lifecycle that includes creation, starting, stopping, and removal.

- **Creating a Container**: The `docker run` command is used to create and start a new container from an image.
- **Starting a Container**: A container can be started with the `docker start` command if it's in a stopped state.
- **Stopping a Container**: The `docker stop` command gracefully stops a running container.
- **Removing a Container**: The `docker rm` command removes a stopped container. Be cautious as this action is irreversible.

### Container States

Containers can be in various states, including running, stopped, and exited. You can view the state of your containers using the `docker ps` command, which lists running containers, and `docker ps -a`, which lists all containers, including those that have exited.

## Managing Containers

Managing containers involves starting, stopping, viewing logs, interacting with containers, and removing them when they are no longer needed.

### Starting and Stopping Containers (continued)

You can start and stop containers using the `docker start` and `docker stop` commands.

Starting a container:

```
docker start my-container

```

Stopping a container:

```
docker stop my-container
```

Starting a container restarts it in the state it was in before stopping. This can be helpful for services that should automatically recover from failures.

### Viewing Container Logs

Viewing container logs is crucial for monitoring, debugging, and troubleshooting applications. You can use the `docker logs` command to access container log output.

For example:

```
docker logs my-container
```

By default, you'll see the standard output and error streams from the container. The `-f` option allows you to follow the log in real-time, which is especially useful for debugging long-running services.

### Interacting with Containers

You can interact with a running container in several ways, including:

1.  **Interactive Shell**: Use the `docker exec` command to run an interactive shell session within the container.

    ```
      docker exec -it my-container /bin/bash
    ```

    This is helpful for running commands or inspecting the container's environment.

2.  **Copying Files**: You can copy files in and out of a container using the `docker cp` command.

    To copy a file from your local machine to a container:

    ```
    docker cp local-file.txt my-container:/container-path/file.txt
    ```

    To copy a file from a container to your local machine:

    ```
    docker cp my-container:/container-path/file.txt local-file.txt
    ```

3.  **Attaching to Standard Streams**: You can attach to a container's standard streams (stdin, stdout, and stderr) using the `docker attach` command.

    ```
    docker attach my-container
    ```

    Keep in mind that this is not an interactive shell but rather a way to attach to the container's I/O streams.

### Removing Containers

When a container is no longer needed, you can remove it using the `docker rm` command. This action is irreversible, so make sure you have backups or snapshots of any data or configurations you need.

```
docker rm my-container
```

If the container is currently running, you can use the `-f` option to forcefully remove it:

```
docker rm -f my-container
```

## Docker Compose

Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to describe your application's services, networks, and volumes in a single YAML file. This simplifies the management of complex applications and their dependencies.

### Creating a Docker Compose File

A Docker Compose file, typically named `docker-compose.yml`, defines the services that make up your application. You can specify which images to use, which ports to expose, and how the services interact.

Here's a simple example of a Docker Compose file for a web application and a database:

## Docker Compose Example

In this section, we'll provide an example of a Docker Compose file that defines two services: a web server using the Nginx image and a MySQL database.

```yaml
version: "3"
services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: example
```

In this example, we have two services, one for the web server and another for the database. The `web` service uses the Nginx image and exposes port 80 on the host, while the `db` service uses the MySQL image and sets an environment variable for the root password.

### Running Docker Compose

To run services defined in a Docker Compose file, use the `docker-compose up` command:

```
docker-compose up
```

Docker Compose will create and start the specified services, and you can see the logs from all containers in real-time. You can use the `-d` flag to run the services in detached mode.

```
docker-compose up -d
```

To stop and remove the containers defined in the Compose file, use the `docker-compose down` command:

```
docker-compose down
```

Docker Compose simplifies the management of multi-container applications, making it easier to maintain complex setups.

## Docker Networking

Docker provides several networking options for containers, allowing you to control how they communicate and isolate them from each other.

### Docker Bridge Network

By default, when you run a container, it is connected to the bridge network. Containers on the bridge network can communicate with each other, but they are isolated from the host machine's network. This is useful for many scenarios, but it can also limit communication in some cases.

### Custom Networks

Docker allows you to create custom user-defined networks, providing more control over container communication. This is particularly useful when running multiple containers that need to interact in a specific way.

You can create a custom network using the `docker network create` command:

```
docker network create my-network
```

Once the network is created, you can connect containers to it by specifying the network name when starting a container:

```
docker run -d --network my-network my-container`
```

This allows containers on the same network to communicate with each other by their container name.

### Container Communication

Containers on the same network can communicate with each other using their container names as hostnames. For example, if you have two containers, `web` and `db`, both connected to the same custom network, the `web` container can reach the `db` container using `db` as the hostname.

Custom networks are valuable when building multi-service applications where containers need to communicate securely and efficiently.

## Docker Volumes

Docker volumes are used to persist data between container runs. They are essential for managing data that should not be stored within the container's filesystem. Volumes enable you to handle data related to databases, logs, and other persistent requirements.

### Data Persistence

In a typical container, any data written to the container's filesystem is lost when the container is removed. However, by using volumes, you can ensure that your data persists even if the container is deleted or replaced.

Volumes are particularly useful for database containers, where you want to ensure data consistency and availability.

### Volume Types

Docker provides several types of volumes, including:

1.  **Named Volumes**: These are created using the `docker volume create` command and given a user-defined name. Named volumes are often preferred for their simplicity and flexibility.
2.  **Host Bind Mounts**: These volumes link a directory or file from the host machine to a container. Host bind mounts are useful when you need to provide access to specific files or directories from the host to the container.
3.  **Anonymous Volumes**: Anonymous volumes are created automatically by Docker and are associated with a specific container. They are typically used for temporary or cache-like storage.

Using Docker volumes, you can manage data more effectively and ensure that your applications have access to the necessary data even when containers are recreated or moved between different environments.

## Docker Swarm

Docker Swarm is a native clustering and orchestration solution for Docker. It allows you to create a swarm of Docker nodes that can run containers in a highly available and scalable manner. Swarm is a way to manage containerized applications on a cluster of machines.

### Swarm Mode

Swarm mode is an integrated orchestration solution provided by Docker. It turns a group of Docker hosts into a single virtual Docker host,
of Docker hosts into a single virtual Docker host, collectively referred to as a "swarm." This allows you to manage containers across multiple nodes, providing high availability, load balancing, and fault tolerance for your applications.

Swarm mode includes several key components:

1.  **Manager Nodes**: Manager nodes are responsible for orchestrating the swarm, managing service deployment, and maintaining the desired state. A swarm typically has multiple manager nodes for redundancy.
2.  **Worker Nodes**: Worker nodes are responsible for executing tasks and running containers. They receive workloads from manager nodes and ensure the desired number of replicas are running.
3.  **Services**: In swarm mode, you define services, which are sets of containers running the same application. Services enable you to specify the desired state, such as the number of replicas, update policies, and network attachments.

### Service Deployment

Deploying services in a swarm is straightforward. You define a service in a Compose file and deploy it to the swarm using the `docker stack deploy` command:

```
docker stack deploy -c my-compose.yml my-stack`
```

This command deploys the services defined in the Compose file to the swarm under the specified stack name. The services are distributed across the worker nodes in the swarm.

### Scaling Services

One of the advantages of using swarm mode is the ease of scaling services. You can scale services up or down by adjusting the number of replicas. Swarm mode ensures that the desired number of replicas is maintained even if nodes fail.

For example, to scale a service to four replicas:

```
docker service scale my-service=4
```

Swarm mode will distribute the replicas across the available worker nodes to provide redundancy and high availability.

## Docker Security

Docker security is a critical consideration, as containers share the same host kernel and run in an isolated environment. Here are some important aspects of Docker security:

### Image Security

Docker images are the foundation of containers. To ensure image security:

- Regularly update base images to receive security patches and updates.
- Use signed images to verify their authenticity.
- Scan images for vulnerabilities using tools like Clair, Trivy, or Docker Security Scanning.
- Minimize the number of unnecessary layers in your Dockerfile to reduce potential vulnerabilities.

### Container Isolation

Containers are designed to be isolated from each other and from the host system. However, to enhance container isolation:

- Limit container privileges by avoiding running containers as the root user.
- Utilize user namespaces to map container users to non-privileged users on the host.
- Apply seccomp profiles to restrict system calls that containers can use.
- Use AppArmor or SELinux to implement mandatory access controls.

### Secure Configuration

Ensure that your containers and Docker environment are configured securely:

- Implement network segmentation to separate containers with sensitive data from public-facing services.
- Restrict container capabilities using the `--cap-drop` flag in the `docker run` command.
- Set resource limits to prevent containers from monopolizing system resources.
- Apply least privilege principles when defining user roles and permissions.

Following best practices for image and container security is essential to reduce the risk of vulnerabilities and ensure a secure Docker environment.

## Docker Best Practices

Docker best practices are guidelines that help you make the most of Docker while minimizing potential issues:

### Image Management

- Keep your images lightweight by minimizing the number of layers in your Dockerfile.
- Use multi-stage builds to create smaller images and reduce attack surfaces.
- Regularly update your base images to benefit from security patches and improvements.
- Organize images in a registry for versioning and easy access.

### Container Orchestration

- Use Docker Compose for local development and testing to define complex application stacks.
- Implement container orchestration platforms like Docker Swarm or Kubernetes for production deployments.
- Define service replicas to ensure high availability and load balancing.
- Leverage health checks to monitor and automatically recover from container failures.

### System Optimization

- Optimize Docker resource limits to ensure fair resource allocation among containers.
- Use logging drivers to forward container logs to external logging systems.
- Consider implementing container monitoring tools like Prometheus and Grafana.
- Keep the Docker host and system up-to-date with security patches.

Properly implementing these best practices will help you create a stable and efficient Docker environment for your applications.

## Troubleshooting

Docker is a powerful tool, but like any technology, it can encounter issues. Troubleshooting is an essential skill for Docker users. Here are some common problems and their solutions:

### Container Crashes

- **Check Logs**: Examine container logs using `docker logs <container_id>` to identify error messages and issues.
- **Inspect Resource Limits**: Verify that resource limits (CPU, memory) are appropriately set to avoid container crashes.
- **Check Dependencies**: Ensure that all required dependencies and external services are accessible and correctly configured.
- **Verify Image Compatibility**: Confirm that the base image and application dependencies are compatible.

### Networking Issues

- **Container Connectivity**: Use `docker network inspect` to check that containers are on the same network.
- **Port Conflicts**: Make sure that container ports do not conflict with ports in use by other applications.
- **DNS Resolution**: Test DNS resolution within containers to ensure proper network connectivity.
- **Firewall Rules**: Ensure that firewall rules permit the necessary network traffic.

### Resource Constraints

- **Resource Monitoring**: Use Docker stats to monitor resource usage and identify containers consuming excessive resources.
- **Adjust Resource Limits**: Modify resource limits for containers to prevent resource contention.
- **Scaling**: Consider scaling services horizontally to distribute workloads and reduce resource bottlenecks.
- **Optimize Images**: Minimize image size and remove unnecessary dependencies to reduce resource utilization.

## Docker Ecosystem

Docker is part of a broader container ecosystem that includes complementary tools and technologies. Here are some essential components of the Docker ecosystem:

### Kubernetes and Docker

Kubernetes is a powerful container orchestration platform that can manage Docker containers. It provides features for scaling, load balancing, and automated deployment. Many organizations use Kubernetes in conjunction with Docker to manage containerized applications at scale.

### CI/CD with Docker

Continuous Integration/Continuous Deployment (CI/CD) pipelines benefit from Docker's consistency and portability. Docker images are commonly used in CI/CD processes to build, test, and deploy applications efficiently.

### Monitoring Docker

Monitoring tools like Prometheus, Grafana, and ELK Stack are used to track container performance and health. These tools allow you to gain insights into resource usage, container status, and application behavior.

---

## Summarizing Commands

### Docker Basic

- To check Docker version

```
docker version
```

- To check all the available images

```bash
docker images
```

- Pull/Download the image from the Docker registry to local machine.

```bash
docker pull <image name>
//Eg: docker pull nginx
```

- To run an container (It will 1st pull the image if not present in the local sytem)

  - NOTE: When we just provide the name of the image it will pull the latest one, i.e `nginx:latest`. We can also specify the version `nginx:1.14`
  - Additioanly we can use flags

    - `--name <name> `- To give a name to the container.
    - `-p <Host port:container port>`- To fowrad the port.
    - `-d` - To run in detached mode
    - `-it` - For interactive envirnoment
    - `-e` - For environment variable

```bash
docker run <image-name>
//Eg: docker run nginx
```

- We can also pass a complete `.env` file

```bash
--env-file <path-to-env-file>
Eg: --env-file ./.env
```

### Docker Container

- To stop a running container

```bash
docker stop <container-ID/name>
```

- To resume a stopped container

```bash
docker start <container-ID/name>
```

- To check the running processes inside a container.

```bash
docker top <container-name/id>
```

- To check stats of running container.

```bash
docker stats <container-name/id>
```

- Check the config and info of a container.

```bash
docker inspect <container-name/id>
//Eg: docker inspect mynginx
```

- Check all the container running.

```bash
docker ps
or
docker container ls
```

- To start and interactive session and attach terminal with the container.

  - NOTE: every image does not support `bash` so we should use `sh`

```
docker exec -it <container-ID/name> bash/sh
```

- To check which ports has been exposed and forwarded

```bash
docker port <image-name>
```

- To check all the containers (stopped, paused and running)

```bash
docker ps -a
```

- Check logs of a container

```bash
docker logs <container-ID/name>
```

- Delete all the stopped containers

```bash
docker container prune -f
```

- Delete all the containers (stopped, paused and running)

```bash
docker rm -f $(docker ps -aq)
```

- Delete all the images

```bash
docker rmi -f $(docker images -q)
```

- Remove unused images

```bash
docker image prune -all
```

- Auto cleanup when the container exits

```bash
 docker container run —rm <image-name>
```

### Docker Network

- Check list of avilable networks.

```bash
docker network ls
```

- Inspect a network components, like which container are attached to that network.

```bash
docker network inspect <network-name>
```

- Run a container on a certian network/own careted network

```
docker run --network <network-name> <image-name>
```

```
docker inspect --format "{{.NetworkSettings.IPAddress}}" <container-name>
```

### Docker Images

- Remove an image

```bash
docker rmi <image name> -f
```

- Remove all the images at once

```bash
docker rmi $(docker images -q)
```

- To inspect an image layers and other info

```bash
docker inspect  <image-name/id>
```

- Check the image layers formation

```bash
docker history <image-name/id>
```

- Create a our own image with an existing image.

```
docker image tag <image-name:tag> <new-image-name:tag>
docker image tag nginx pradumna/nginx:hello
docker image tag ubuntu:18.04 pradumna/ubuntu:example
```

### Docker Volume

- Create bind mount

  - Help to sync our local files with help of Docker container.

- To sync our local machine changes with help of Docker volume (Bind mount)
  - `- v` is use to define volume, also we give another `-v` flag to override the changes so that it will not chnage in container.

```bash
docker run -v <path-to-folder-on-local-machine>:<path-to-folder-on-container> -p <host-port>:<container-port> -d --name docker-node docker-node
docker
```

```bash
docker run -v <path-to-folder-on-local-machine>:<path-to-folder-on-container> -v <path-to-file/folder-on-container> -p <local-machine-port>:<container-port> -d --name docker-node docker-node
```

To make it read only so that when you add some files inside it, the container will not get created on your local machine use `-v port:port:ro`

### Docker Compose

- Run docker compose file.
  Note: By default it finds for the file name `docker-compose.yaml`, to give file with other naming use `-f <file-name.yaml>` command

```bash
docker compose up -d
```

```bash
docker compose down
```

- To rebuilt the new Image with thew new changes

```bash
docker compose up --build
```

- Override the existing of compose file

```bash
docker compose -f docker-compose.yaml  -f docker-compose.dev.yaml
```

### Docker Swarm and Services

- Initalize swarm

```bash
docker swarm init
```

- Check all the node available

```bash
docker node ls
```

- To add a node as a manager

```bash
docker node update --role manager <node-name>
```

- To create an overlay network

```bash
docker network create -d overlay backend
```

- Create a service. Also we can add flags for further customization.

  - `--name` - to give a service name
  - `--replicas` - to define how many running instance of the same image.
  - `-p` - for port forwarding

```bash
docker service create -p 8080:80 --name vote --replicas 2 nginx
```

- To get all task containers running on different node

```bash
docker service ps <service-name/id>
```

> SERVICE UPDATE

- To scale up the service (i.e increasing the no of replicas)

```bash
docker service scale <service name>=<no to scale>
docker service scale mynginx=5
```

- To update the image in running service

```bash
docker service update --image <updated image> <service name>
docker service update --image mynginx:1.13.6  web
```

- To update the port

We can't directly update the port We have to add and remove the ports

```
docker service update --publish-rm 8080 --publish-add 808180 <service name>
docker service update --publish-rm 8080 --publish-add 808180 mynginx
```

### Docker Stack

- To deploy a stack file

```bash
docker stack deploy -c <file-name.yaml> <stackname>
```

- To remove running stack

```
docker stack rm <stack name>
```

- To check list of stacks running

```
docker stack ls
```

**STACK -> SERVICES -> TASKS -> CONTAINERS**

- To check which services are running inside a staacks

```
docker stack services <stack name>
```

- To check taks are running inside a stack

```
docker stack ps <stack name>
```

> Registry

```
127.0.0.0:5000/v2/_catalog
```

### Tips and Short hands

- Run the command with the container creation

```bash
doc run <image-name> <command>
// Eg: `doc run ubuntu:16.04 echo hey`
```

- Creating our Own image and container.

```
Step 1 - create Dockerfile
Step 2 - docker build -t myimage:1.0 <path-of-dockerfile> (-t for tag)
Step 3 - docker run myimage:1.0
```

## Conclusion

Docker is a game-changing technology that has revolutionized the way we develop, ship, and run applications. Its advantages in terms of consistency, isolation, portability, efficiency, and scalability make it an essential tool for modern software development and deployment.

By mastering the fundamental concepts of Docker, understanding its best practices, and effectively troubleshooting issues, you can harness the full potential of containerization and streamline your development and deployment processes. Docker, together with its ecosystem of tools and technologies, empowers you to build, ship, and scale applications with confidence and agility.

As you explore Docker further, remember that it's a dynamic and rapidly evolving field. Stay up-to-date with the latest developments, best practices, and security measures to ensure that your containerized applications remain secure, efficient, and resilient in ever-changing environments.
