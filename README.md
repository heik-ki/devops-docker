# devops-docker

## Exercise 1.1 Getting started

```bash
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                      PORTS     NAMES

b5503e7e92bf   nginx     "/docker-entrypoint.…"   48 seconds ago       Exited (0) 19 seconds ago             compassionate_ellis

4c00e140644a   nginx     "/docker-entrypoint.…"   54 seconds ago       Exited (0) 12 seconds ago             thirsty_austin

3154701efcde   nginx     "/docker-entrypoint.…"   About a minute ago   Up 58 seconds               80/tcp    ecstatic_brahmagupta
```

## Exercise 1.2 Cleanup

```bash

$ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES


$ docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE

```

## Exercise 1.3 Secret message

<code>docker run -d -it --name messenger devopsdockeruh/simple-web-service:ubuntu</code>

Secret message is: 'You can find the source code here: https://github.com/docker-hy'
