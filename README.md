# docker-cheat-sheet
Docker cheat sheet


Remove all images

$ docker rmi $(docker images -a -q)


Remove all stopped containers

docker rm $(docker ps -a -q)
