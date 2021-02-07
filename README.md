# Node + Express + Vue + MySQL + Docker Compose
A project that runs a Express server and Vue-CLI with two separate containers, server and client, using Docker Compose.

# development
```
docker-compose up -d
```
The `/client` and `/server` directries have their own Dockerfile, which are configured with docker-compose.yml.

## Client ports
```
ports: 
     - "8080:8080"
```
The client server is spun up at localhost:8080.
## Server ports
```
ports: 
     - "3000:3000"
```
The server is spun up at localhost:3000.

# Setup
1. RUN `docker-compose build`.  It will pull a base image from the Docker registry.Three images named `myapp-client`, `myapp-server` and `mysql`, will be created.

2. RUN `docker-compose up -d`. It will create container named `myapp` contains `myapp_app-db_1`, `myapp_server_1` and `myapp_client_1`, and will start containers.

# Notes
If you want to install some package using npm, please go into the container and install it.

`--rm`: It will delete the container when it is stopped.

## Client

```
docker-compose run --rm client /bin/bash
```

## Server

```
docker-compose run --rm server /bin/bash
```

# References
- https://github.com/nodejs/docker-node
- https://github.com/b00giZm/docker-compose-nodejs-examples
- https://docs.docker.jp/index.html
- https://nodejs.org/ja/docs/guides/nodejs-docker-webapp/