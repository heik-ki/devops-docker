# devops-docker

## Exercise 1.1: Getting started

```bash
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                      PORTS     NAMES

b5503e7e92bf   nginx     "/docker-entrypoint.…"   48 seconds ago       Exited (0) 19 seconds ago             compassionate_ellis

4c00e140644a   nginx     "/docker-entrypoint.…"   54 seconds ago       Exited (0) 12 seconds ago             thirsty_austin

3154701efcde   nginx     "/docker-entrypoint.…"   About a minute ago   Up 58 seconds               80/tcp    ecstatic_brahmagupta
```

## Exercise 1.2: Cleanup

```bash

$ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES


$ docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE

```

## Exercise 1.3: Secret message

```bash
$ docker run -d -it --name messenger devopsdockeruh/simple-web-service:ubuntu

$ docker exec -it messenger bash
  # tail -f ./text.log

Secret message is: 'You can find the source code here: https://github.com/docker-hy'

```

## Exercise 1.4: Missing dependencies

```bash

$ docker run -d --rm -it --name website ubuntu sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'

```

```bash
$ docker exec -it website bash
  # apt-get update
  # apt-get -y install curl

```

```bash
$ docker attach website
helsinki.fi
Searching..
<html>
<head><title>301 Moved Permanently</title></head>
<body>
<center><h1>301 Moved Permanently</h1></center>
<hr><center>nginx/1.20.1</center>
</body>
</html>
```

## Exercise 1.5: Sizes of images

```bash

$ docker pull devopsdockeruh/simple-web-service:ubuntu
$ docker pull devopsdockeruh/simple-web-service:alpine

```

```bash

$ docker images
REPOSITORY                          TAG       IMAGE ID       CREATED       SIZE
devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   2 years ago   83MB
devopsdockeruh/simple-web-service   alpine    fd312adc88e0   2 years ago   15.7MB

```

The size of Ubuntu-based image is over five times larger than the size of Alpine-based image.

```bash

$ docker run -d -it --name alpineweb devopsdockeruh/simple-web-service:alpine
$ docker exec -it alpineweb sh
  # tail -f ./text.log

Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```

## Exercise 1.6: Hello Docker hub

```bash

$ docker run -it devopsdockeruh/pull_exercise

```

Password from https://hub.docker.com/r/devopsdockeruh/pull_exercise

Secret message is: "This is the secret message"

## Exercise 1.7: Image for script

[Dockerfile](/part1/Exercise-1_7/Dockerfile)


## Exercise 1.8: Two line Dockerfile

[Dockerfile](/part1/Exercise-1_8/Dockerfile)

The command to run the container: 
```bash
$ docker run web-server
```

## Exercise 1.9: Volumes

Commands:

```bash
$ touch text.log
$ docker run -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
```
## Exercise 1.10: Ports open

```bash
$ docker run -p 8080:8080 web-server
```
In browser:
http://localhost:8080

## Exercise 1.11: Spring

[Dockerfile](/part1/Exercise-1_11/Dockerfile)

## Exercise 1.12: Hello, frontend!

[Dockerfile](/part1/Exercise-1_12/Dockerfile)

## Exercise 1.13: Hello, backend!

[Dockerfile](/part1/Exercise-1_13/Dockerfile)

Command used:

```bash
$ docker build . -t example-backend && docker run -p 8080:8080 example-backend
```
