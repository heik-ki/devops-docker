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

<code>docker run -d -it --name messenger devopsdockeruh/simple-web-service:ubuntu</code>

Secret message is: 'You can find the source code here: https://github.com/docker-hy'

## Exercise 1.4: Missing dependencies

```bash

$ docker run -d --rm -it --name website ubuntu sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'

```

```bash
$ docker exec -it website bash
root@42d2bede8135:/# apt-get update
root@42d2bede8135:/# apt-get -y install curl

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


