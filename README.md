# DockerCheatSheet
Cheat Sheet with docker commands I use regularly

## Views

View services

    $ docker ps
    
    Useful args:
    -a = all
    -q = just show id
    
View downloaded images
    
    $ docker images
    
View volumes

    $ docker volume ls
    
View networks

    $ docker network ls

View machines

    $ docker-machine ls
    

## Deleting

Delete all running services

    $ docker rm $(docker ps -q)
    
Delete all services running and stopped

    $ docker rm $(docker ps -aq)
    
Delete all volumes

    $ docker volume rm $(docker volume ls -q)
    
Delete all images

    $ docker rmi $(docker images -q)
    
Combine delete commands - stop all services, remove all services, remove volumes

    $ docker stop $(docker ps -qa) && docker rm $(docker ps -aq) && docker volume rm $(docker volume ls -q)
    
## Debugging

Access bash

    $ docker exec -it CONTAINER_ID bash
    
View services running inside continer

    $ docker exec -it CONTAINER_ID ps aux
    
Remove an entire machine (eg default) and set it up again

    $ docker-machine rm ENVIRONMENT_NAME
    eg
    $ docker-machine rm default
    
    $ docker-machine create ENVIRONMENT_NAME
    or
    $ docker-machine create --driver virtualbox default
    
    

## Docker machine commands
    
    $ docker-machine inspect
    $ docker-machine rm default
    $ docker-machine ls
    $ docker-machine create default
    $ docker-machine create --driver virtualbox default
    $ docker-machine ip
    
    
    
# Linux commands

## Useful linux commands

### Search

Search for files with extension eg .hpi

    find . -name *.hpi*
    
Syntax

    find [location] -n [matcher]
    
### IP

When on digital ocean and you want to see the IP of the server:

    ip addr show
    
Look for one of the "inet" rows ends with "scope global eth0"
    
