
# Docker composer basics

## Lets make folders (Windows)

    mkdir -p c:\docker\weptop
    mkdir -p c:\docker\mount
    mkdir -p c:\docker\traefik
    mkdir -p c:\docker\logs

#### Mac computer only

    cd ~
    mkdir docker
    cd docker 
    mkdir weptop
    mkdir mount
    mkdir traefik
    mkdir logs
    

## Create a Docker composer file

### Manual way
    nano docker-compose.yml

    OR

    code docker-compose.yml

    OR
### Automation
    cd c:\docker\traefik

    Invoke-WebRequest -Uri https://raw.githubusercontent.com/TeroKeso/Traefik_2024/main/2-traefik.yml -OutFile docker-compose.yml -UseBasicParsing
    
    MAC
    curl https://raw.githubusercontent.com/TeroKeso/Traefik_2024/main/2-traefik.yml --output docker-compose.yml
    


# Start a docker composer prosess by reading docker-compose.yml

    docker-compose up -d

# Let's read docker-composer log and docker prosess 
  
    docker-compose logs
    docker ps
    docker inspect CONTAINER_NAMEs

# Docker-compose up and scale

    docker-compose up -d
    docker-compose up --scale whoami=2 -d
    docker-compose up --scale whoami=3 -d
 
 # Docker stop and remove container

    docker ps 
    docker stop CONTAINERNAME / ID
    docker rm CONTAINERNAME / ID


# Update docker Composer image

    docker-compose pull
    docker-compose up -d

# Clean all non used images, containers and networks
  
    docker system prune 
   

# *Extra* voluntary docker network practices. This will need to done on your own linux computer and network

You cant do this in HAMK network because you don't know network range and ALL ip are being given out with DHCP server. 

[How to use macvlan networks](https://docs.docker.com/network/macvlan/)

## Docker network commands

    docker network ls
    docker network create -d macvlan-subnet 192.168.0.0/24 -gateway 192.168.0.1 -ip-range 192.168.0.253/32 -o parent=eth0 custommacvlannetworkwemade

    
