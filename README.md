# Simple Node.js app on Docker

Based on: https://nodejs.org/en/docs/guides/nodejs-docker-webapp/

## build docker image
```
# tags as latest
docker build -t simple-node-app .

# or custom version
export VERSION=0.0.1
docker build -t simple-node-app:$VERSION .

# and tag as latest
docker tag simple-node-app:${VERSION} simple-node-app:latest
```

## run image (latest)
```
docker run -it --rm -p 49160:8080 simple-node-app

# where:
# -it   for interactive processes (like a shell)
# --rm  clean up (automatically clean up the container and remove the file system when the container exits)
# -p    maps public port to container private port

```

## More:
Print the output of your app:

```
# Get container ID
$ docker ps

# Print app output
$ docker logs <container id>

# If you need to go inside the container you can use the exec command:
$ docker exec -it <container id> /bin/bash
```
