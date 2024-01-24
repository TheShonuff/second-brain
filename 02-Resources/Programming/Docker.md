---
tags:
  - virtual
---
# Docker
- Arch installation
	- `yay -S docker`
	- `systemctl start docker.socket`
- verify installation of docker using `docker run hello-world`

## Run without sudo
- `sudo groupadd docker`
- `sudo usermod -aG docker $USER`
- to activate without logging out `newgrp docker` 
- Test `docker run hello-world`

## mongoDB
[reference](https://hub.docker.com/_/mongo)

```sh
docker run -d -p 27017:27017 --name test-mongo mongo:latest

# Docker
docker run -d --name test-mongo mongo:latest --port 8000

#run interactive shell
docker exec -it test-mongo bash

#restart a docker
docker restart test-mongo

#stop a docker
docker stop test-mongo

#kill a docker
docker kill test-mongo

#force remove a runnign container
docker rm --force test-mongo


```


