
Docer Swarm

Swarm: a cluster of one or more docker engines

Node: the computer running Docker Engine instance

Manager Node: Responsible for cluster management and Orchestration

Worker Node: Responsible for running tasks on services

Service: a collection of one or more containers with the same role

commands
==========

docker swarm init

To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-2os619qu18wxvu5pjxirvksdsetr8cyiye8h4cso1yrcv4f6pu-9b6uwdf18kgsfz0l8v1dt3ul0 192.168.0.183:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.

docker service create -d --name <<service_name>> -p port:port <<image_name>>


docker service ls

docker service scale <<service_name>>=3

docker service ls

docker container ls

docker container stop <<container_id>>

docker container ls

docker service rm <<service_name>>


docker network create --driver overlay <<network_name>>


docker network ls


docker service create -d --replicas 1 --name db_server --network blog_network --mount type=volume,source=database_volume,destination=/data/db_mydb mydb


docker service create -d --name app_server --replicas 3 --network blog_network myapp_swarm

docker container exec -it <<container_id>> /bin/bash

cat /etc/resolv.conf

resolver 127.0.0.11 ipv6=off valid=10s;

docker service create -d --name web_server --replicas 3 --network blog_network -p 8080:80 myweb_swarm





docker stack
=============

Create a yml file with services.



command
=========

docker stack deploy -c blog_swarm.yml blog_swarm



















