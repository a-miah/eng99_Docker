# Docker

## What is Docker
- Docker is an open platform for developing, shipping, and running applications
- Docker enables you to separate your applications from your infrastructure so you can deliver software quickly.
- Docker provides the ability to package and run an application in a loosely isolated environment called a container.
- Containers are lightweight and contain everything needed to run the application, so you do not need to rely on what is currently installed on the host.


## Docker vs VMs
- Under a VM environment, each workload needs a complete OS. But with a container environment, multiple workloads can run with 1 OS
- VMs are a better choice for running apps that require all of the operating system’s resources and functionality when you need to run multiple applications on servers, or have a wide variety of operating systems to manage.
- Containers are a better choice when your biggest priority is maximizing the number of applications running on a minimal number of servers.

## Benefits of Docker
- Simplicity and Faster Configurations
- Rapid Deployment
- Continuous Deployment and Testing
- Multi-Cloud Platforms

## Microservices Architecture
Microservices architecture structures an application as a collection of services that are:
- Highly maintainable and testable
- Loosely coupled
- Independently deployable
- Organized around business capabilities
- Ownedby a small team

## Installing Docker
- Install docker on windows - https://docs.docker.com/desktop/windows/install/

## Login
- Linking account and terminal - `docker login`

## Docker Commands
- `docker images`
Docker image is a package of a container
- `docker pull image-name` - pulls image from docker hub
- `docker run image-name` - runs an image
- `docker build -t image-name`
- `docker push image-name`
- `docker run -d -p 2368:2368 ghost` - # need to check official docs to find port for image
- `docker stop` - stops running a container
- `docker kill` - kills container
- `docker image rm <image name>` - removes image
- `docker rm <container id> -f` - removes container

How to check running container:
- `docker ps` and `docker ps -a`

## Docker Docs on localhost
`docker run -d -p 4000:4000 docs/docker/gihub/io`

## Logging into a container
- `docker exec -it <container-id> bash` - goes into container
- `apt update -y`
- `apt install nano`
- `cd /usr/share/nginx/html/`
- `nano index.html`

## Ports
`docker run -d -p <localhost port>:<container-port>`

## Uploading to Dockerhub
### Commit
- `docker commit <docker ps instance name> <dockerhub-id>/<repo-name>:[tags]`
- If tags left empty default is latest version

### Push to docker hub
- `docker push <dockerhub id>/<repo-name>:[tags]`

## Copying files into container
- `docker cp <filename> <container id>:<file path within container>`
- EG: `docker cp index.html <container id>:/usr/share/nginx/html` - copies index.html into html folder
