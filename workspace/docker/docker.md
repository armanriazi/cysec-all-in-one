
## Local Deploy

```bash
docker run --rm -it -v ${PWD}:/docs armanriazi.jfrog.io/default-docker-virtual/squidfunk/mkdocs-material:202204 build
```

```bash
docker tag local-image:tagname new-repo:tagname
```

```bash
docker push armanriazi2blockchain/armanriazi2blockchain:tagname
```

```bash
docker exec -it -u root node-docker /bin/bash
```

```bash
docker run -it autodevops.dynv6.net:5000/mongo:4
```

```bash
chmod 777 /home/user/.docker
```

---

# Sample Config & Commands

## Gateway

## portainer

```bash
docker volume create portainer_data
docker run -d --name portainer-localhost --network=gateway-localhost -p 8000:8000 -p 9443:9443 --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data localhost:5000/portainer/portainer-ce:latest
```

### OTEL

```bash
docker run --name grafana-otel-lgtm_localhost --network=gateway-localhost -p 3000:3000 -p 4317:4317 -p 4318:4318
```

### PgAdmin4

```bash
docker run --name pg-dashboard_localhost --network=gateway-localhost -p 5488:80 -e PGADMIN_DEFAULT_EMAIL=armanriazi.service@gmail.com -e PGADMIN_DEFAULT_PASSWORD=SUqazE#7752235 -d localhost:5000/dpage/pgadmin4
```

### Postgres

```bash
docker volume create pg_data
docker run --name postgres_arvancloud --network=gateway-localhost -p 5432:5432 -v pg_data:/var/lib/postgresql/data -e POSTGRES_PASSWORD=postgres -e POSTGRES_USER=postgres -e POSTGRES_DB=postgres -d docker.arvancloud.ir/postgres
```

### Redis-Stack

```bash
docker run -d --network=gateway-localhost --name redis-stack -p 6379:6379 -p 8001:8001 -e REDIS_ARGS="--requirepass mypassword" docker.arvancloud.ir/redis/redis-stack:latest
```

### RabbitMQ

```bash
docker volume create rmq_plugins
docker run -d --hostname localhost --network=gateway-localhost --name rabbitmq_arvancloud -v rmq_plugins:/usr/lib/rabbitmq/plugins -p 15672:15672 -p 5672:5672 -p 25676:25676 docker.arvancloud.ir/rabbitmq:3-management
```

## Install

```bash
https://docs.docker.com/install/linux/docker-ce/ubuntu/
```

## Service,Journal

```bash
journalctl -u docker
sudo /etc/init.d/docker restart

systemctl daemon-reload && systemctl restart kubelet && sleep 5 && systemctl status kubelet
systemctl daemon-reload && systemctl restart docker && sleep 5 && systemctl status docker.service
```

```bash
docker images
docker pull dockerup/quicksite:latest
docker ps -a
docker container ls --all  or docker container ls --all
docker start/stop/restart containerid
```

## FileSystem

```bash
cat /proc/filesystems | grep cgroup
sudo chgrp docker /usr/bin/docker
sudo chgrp docker /var/run/docker.sock
docker save -o ubuntu.tar ubuntu  => OR docker export ...
docker load -i ubuntu.tar
```

## Volumn

```bash
docker volume rm $(docker volume ls -qf dangling=true)
docker system prune --volumes
docker volume ls
docker volume inspect nameofvolume
docker volume rm data


docker volume rm $(docker volume ls -qf dangling=true)
docker system prune --all
docker system prune --all --volumes
```

## User

```bash
sudo groupadd docker
sudo gpasswd -a ubuntu1604rzero docker
sudo usermod -aG docker [username]
```

## Network

```bash
Get-NetIPAddress –AddressFamily IPv4
Get-WMIObject Win32_Bios
Get-NetIPAddress 192.168.99.100 | Select-Object 
docker  --tlscert="C:\Users\a_riazi\.docker\machine\certs"
docker network ls 
docker network inspect networkid
netstat -aon | findstr :"53"
```

## Build,Run,Exec

```bash
docker build --rm -f Dockerfile -t hello:latest .
docker build -t mssqlcli E:\g=> Run DockerFiles - g cotaine a DockerFile
docker run -it --name master -p 9090:80 -v backup:/backup -v logs:/logs -v //d/dev/projectname/.:/usr/src/app/projectname
docker build -t projectname -f ./.Dockerfile .
docker run -td --name webserver -p 80:80 ubuntu 
docker port webserver
docker attach conatinername
docker run -it -e MODE=test ubuntu bash
echo $MODE
vi env.list
docker run -it --env-file ./env.list ubuntu bash
docker run -it --env-file ./env.list -e MODE=dev ubuntu bash
docker run -d -p 80:80 dockerup/quicksite
docker run -it imageid /bin/bash
docker commit containerid ubuntu-npm=>create clone image
docker run -it containerid npm -v
docker run -it -h test.local ubuntu bash
docker exec -it containerid /bin/bash
docker exec -it containerid php -a
docker exec -it -u armanriazi containername/bin/bash
docker cp main:/text.txt .
docker run -td --name webserver -p 80:80 containername => webserver is a new imagename
docke port containername
docker run -it --name formap -v ~/a_riazi@a_riazi/data:/data ubuntu bash
docker run -it --name master -v backup:/backup -v logs:/logs ubuntu bash
docker run -it --name slave1 --volumes-from master ubuntu bash
docker run --name wordpress --link mysql:latest -p 8080:80 -d wordpress
```

## Remove,Rename

```bash
docker rename containerid beborename aftername
docker rmi imagesid
docker rm containerid
docker rm -f test2 => remove file by docker
```

## Debug,Log,Ins

```bash
docker inspect containername
docker  container  inspect containerid
docker logns containerid => show whole executed commands
```

## Search Filter

```bash
docker ps --filter "status=running" 
docker search --filter=stars=99 mysql
docker search --filter=stars=99 --no-trunc mysql
```

```bash
sudo nano /etc/docker/daemon.json=>add to file =>
{
  "insecure-registries" : ["172.18.3.9:5000"]
}
#=>then : docker info
nano /etc/default/docker =>add to file =>insecure-registries=172.18.3.9:5000=>then : docker info
docker service create  --name portainer  --publish 9000:9000  token://df4f8c340340b0a6a389557477ce2c5c  --mount type=bind,src=//var/run/docker.sock,dst=/var/run/docker.sock  portainer/portainer  -H unix:///var/run/docker.sock


#Setup daemon.
cat > /etc/docker/daemon.json <<EOF
{
  "exec-opts": ["native.cgroupdriver=cgroupfs"],
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "100m"
  },
  "storage-driver": "aufs"
}
EOF


mkdir -p /etc/systemd/system/docker.service.d
```

دستورات Docker Swarm

## DockerSwarm

```bash
docker swarm join --token SWMTKN-1-5t75eugx0u471q585kbf5tsl7rekuuhtrsdzzubvq8bn8xpuhk-1x0xscedca5odgxz77muu0f6w 192.168.0.28:2377
```

## Docker-Machine

```bash
docker-machine --debug regenerate-certs -f default
docker-machine regenerate-certs dockerhost1=>before it install openssl

docker-machine stop default
docker-machine start default
docker-machine ip howtocodewell =>or default
docker-machine env default
docker-machine active
docker-machine ls
docker-machine create -d virtualbox default
docker-machine create -d hyperv --hyperv-virtual-switch "Default Switch" manager1
docker-machine rm name
(install machine-directly)
base=https://github.com/docker/machine/releases/download/v0.14.0 &&
  curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
  sudo install /tmp/docker-machine /usr/local/bin/docker-machine   
```

## Docker-compose

```bash
docker-compose up -d
docker-compose down –-volumes
docker-compose -f  ci-build.yaml down --remove-orphans
docker-compose config
```
