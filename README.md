# docker-cheat-sheet
Docker cheat sheet


### Removal

Remove all images

`$ docker rmi $(docker images -a -q)`

Remove all stopped containers

`$ docker rm $(docker ps -a -q)`

Remove all stopped containers and all unused images (even those that are associated with a container)

`$ docker system prune -a`
