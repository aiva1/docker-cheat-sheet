# docker-cheat-sheet
Docker cheat sheet


### Removal

Remove all images

`$ docker rmi $(docker images -a -q)`

Remove all stopped containers

`$ docker rm $(docker ps -a -q)`

Remove all stopped containers and all unused images (even those that are associated with a container)

`$ docker system prune -a`


### Databases

####Postgres

`$ docker pull postgres:10.12`

`$ mkdir -p $HOME/docker/volumes/postgres` <- create local folder for data storage after container is down

`$ docker run --rm --name postgres-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres:10.12`

Connect to Postgres using CLI 

`$ psql -h localhost -U postgres -p 5432 -W`

Note: if there is an issue with using the command
```
   dyld: Library not loaded: /usr/local/opt/openssl/lib/libssl.1.0.0.dylib
   Referenced from: /usr/local/lib/libpq.5.dylib
   Reason: image not found
```

Then commands below could fix it
```bash
$ brew update && brew upgrade
$ brew install openssl
```

