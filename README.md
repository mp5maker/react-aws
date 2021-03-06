## DOCKER INSTALLATION ##
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

## DOCKER UNINSTALL ##
```bash
sudo apt-get purge docker-ce docker-ce-cli containerd.io
sudo rm -rf /var/lib/docker
```

## DOCKER VERSION ##
```bash
docker --version
```

## DOCKER IMAGES ##
```bash
docker image ls
docker images
docker images -q
docker image -a
```

## DOCKER PROCESS STATUS ##
```bash
docker ps --all
```

## DOCKER LOGIN ##
* Login
```bash
docker login
```

## DOCKER BUILD IMAGES ##
```bash
docker build --tag react-aws .
```

## DOCKER RUN ##
```bash
docker pull [image] eg: docker pull alpine
docker run [image] eg: docker run alpine
docker run -it [image] eg: docker run -it alpine
```

## DOCKER EXAMPLE ##
```bash
git clone https://github.com/dockersamples/node-bulletin-board
cd node-bulletin-board/bulletin-board-app
docker build --tag bulletinboard:1.0 .
docker run --publish 8000:8080 --detach --name bb bulletinboard:1.0
docker rm --force bb
```

## DOCKER UTILITIES ##
```bash
docker ps
docker stats
docker stop [container-id]
docker run [container-id]
docker rmi [image] eg: docker rmi alpine
docker system df
docker system prune
```

## PUBLISH ##
--publish asks Docker to forward traffic incoming on the host’s port 8000 to the container’s port 8080.
Containers have their own private set of ports, so if you want to reach one from the network, you have to forward traffic to it in this way.
Otherwise, firewall rules will prevent all network traffic from reaching your container, as a default security posture.

## DETACH ##
--detach asks Docker to run this container in the background.

## NAME ##
--name specifies a name with which you can refer to your container in subsequent commands, in this case bb.

## FORCE ##
--force option stops a running container, so it can be removed.
If you stop the container running with docker stop bb first, then you do not need to use --force to remove it.