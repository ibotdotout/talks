class: center, middle

# Docker - Why everyone talk about Docker ?
###@CoE PSU

---

# Me?

.right[![](https://avatars0.githubusercontent.com/u/686676?v=3&s=460)]

```sh
$ who
> ibot.out
> http://fb.me/botblogblog
> https://github.com/ibotdotout
```
--

```sh
$ do
> Vim
> Git
> Python
> NodeJS
> Automated Testing
> Automated Workflow
> Dev-ops
> Docker
> Agile / XP
```

---

class: center, middle
# What is benefit of Docker ?
## build once, run anywhere

---

# [What is benefit of Docker ?](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/7.0_Release_Notes/sect-Red_Hat_Enterprise_Linux-7.0_Release_Notes-Linux_Containers_with_Docker_Format-Advantages_of_Using_Docker.html)
- Rapid application deployment

- Portability across machines

- Sharing

- Simplified maintenance 

---

class: center, middle
# What is Docker ?
## Container is not lite weight VM

---

# [What is Docker ?](https://www.docker.com/what-docker)

![VM](/img/what-is-docker-diagram.png) < VM  ----  Container > ![Container](/img/what-is-vm-diagram.png)

- a pieceof software in a complete filesystem that contains everything it needs to run: code, runtime, system tools,system libraries 

- This guarantees that it will always run the same, regardless of the environment it is running in.

---

class: center, middle
# Docker Image vs Docker Containers
## like Class and Instance in OOP

---

class: center, middle
# Beyond the Docker
## Docker Ecosystems

---

# [Docker Ecosystems](https://blog.codeship.com/understanding-the-docker-ecosystem/)

.right[![](/img/docker-toolbox.png)]

- Docker Engine  

- Docker Registry / Hub  

- Docker Compose  

- Docker Machine  

- Docker Swarm  

- Docker Toolbox

---

class: center, middle
# Docker with Development
## Same config everywhere

---

class: center, middle
# Docker with Testing
## easy to change version

---

class: center, middle
# First touch with Docker
## Dockerfile and Docker Compose

---

# [Dockerfile](https://docs.docker.com/engine/reference/builder/) - [Best practices](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
# Simple Dockerfile

```sh
FROM debian:sid

RUN apt-get install python

WORKDIR /apps

COPY hello.py /apps/hello.py

CMD python hello.py
```

---

# [Docker Engine](https://docs.docker.com/engine/)

Command

```sh
$ docker ps
$ docker images

$ docker built -t <image-name> .

$ docker run <image-name>
$ docker run -d <image-name>
$ docker run -it --rm  <image-name> <command>

$ docker exec -it <container-id> <command>

$ docker log <container-id>
$ docker inspect <container-id>
$ docker rm <container-id>

$ docker top <container-id>
$ docker stats <container-id>
```

---

# [Docker Compose](https://docs.docker.com/compose/)

- build / pull  
- up / stop / restart / kill / rm  
- run / exec  
- ps / logs  

---

# [Docker Volume](https://docs.docker.com/engine/userguide/containers/dockervolumes/)
## Manage data in containers

---

# [Docker Network](https://docs.docker.com/engine/userguide/networking/dockernetworks/)
## Understand Docker container networks

---

# [Docker Compose File](https://docs.docker.com/compose/compose-file/)
## Write docker-compose.yml

---

class: center, middle
# First touch with Docker
## Workshop and Demo

---

class: center, middle
# Docker to the Cloud
## Docker Machine and Swarm

---

# Docker Machine

---

# Docker Swarm

---

class: center, middle
# Docker to the Cloud
## Demo

---

class: center, middle
# Docker and Microseriver
## Monolithic vs Microservices Architecture

---

# [Monolithic Architecture](http://microservices.io/patterns/monolithic.html)

---

# [Microservices Architecture](http://microservices.io/patterns/monolithic.html)

---

# References:

### Overview about  Software Container / Docker Concept
- [Containers and Future Generations of Clouds - Video Thai](http://www.thaiopenstack.org/conference2016/dr-chanwit-kaewkasi/)

### Where to start ?
- [Docker : ฉบับปูพื้น](http://www.jaynarol.com/what-is-docker/)
- [Docker : ติดตั้งและเริ่มใช้งาน (อย่างเข้าใจ)](http://www.jaynarol.com/understand-docker/)
- [dwyl/learn-docker](https://github.com/dwyl/learn-docker)
- [Awesome-docker -  A curated list of Docker resources and projects](http://veggiemonk.github.io/awesome-docker/)
- [Get Started with Docker](http://docker.com/tryit)
- [Codemy School - Docker for Developers](https://www.youtube.com/playlist?list=PLjQo0sojbbxViGEbI_87SPXpb3neuVqDL)
- [Docker Engine user guide](https://docs.docker.com/engine/userguide/)
- [Docker Training >  Self-Paced Training](https://training.docker.com/self-paced-training)
