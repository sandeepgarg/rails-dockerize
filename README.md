# rails-dockerize
Ruby on Rails application setup using docker

## Local setup

Prepare environment, for dev version you can use the example environment:

```bash
$ cp env-example .env
```

Start the server:

```bash
$ docker-compose up --build
```

Browse http://localhost:8020

## Production image

Prepare production environment, set you production values:

```bash
$ cp env-example .env
```

Build two images:

- drkiq: application
- nginx: http server

```bash
$ docker build --build-arg USER_ID=$(id -u) --build-arg GROUP_ID=$(id -g) -t $DOCKER_USERNAME/rails-dockerize_drkiq:latest -f Dockerfile.production .
$ docker build --build-arg USER_ID=$(id -u) --build-arg GROUP_ID=$(id -g) -t $DOCKER_USERNAME/rails-dockerize_nginx:latest -f Dockerfile.nginx .
```

