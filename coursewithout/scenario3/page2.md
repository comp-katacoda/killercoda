# Running Nginx web server (Tab 1)

In <b>Tab 1</b>, pull the Nginx image from Docker hub. Execute:

> `docker pull nginx`

By default, the command `docker pull nginx` will pull the  image `nginx:latest` where `latest` is the tag of the image. We can pull the Nginx image with specified version (e.g. Version 1.2) by using the image `nginx:1.21`.

Execute in the Docker host's <b>Tab 1</b>:

> `docker pull nginx:1.21`

Verify that the images are downloaded. Execute:

> `docker image ls`

Sample output:
```
REPOSITORY     TAG     IMAGE ID    CREATED     SIZE
nginx      1.21    08b152afcfae    11 days ago     133MB
```

Start an Nginx container. Execute:

> `docker run nginx:1.21`

The nginx server will start up. Sample output:

```
$ docker run nginx
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2021/08/03 04:16:49 [notice] 1#1: using the "epoll" event method
2021/08/03 04:16:49 [notice] 1#1: nginx/1.21.1
2021/08/03 04:16:49 [notice] 1#1: built by gcc 8.3.0 (Debian 8.3.0-6) 
2021/08/03 04:16:49 [notice] 1#1: OS: Linux 4.4.0-193-generic
2021/08/03 04:16:49 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2021/08/03 04:16:49 [notice] 1#1: start worker processes
2021/08/03 04:16:49 [notice] 1#1: start worker process 30
2021/08/03 04:16:49 [notice] 1#1: start worker process 31
```