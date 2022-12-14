# CMD vs. ENTRYPOINT

Modify the "DockerFile" as follows.

```
FROM ubuntu:latest

RUN apt update 
RUN apt install figlet

# ENTRYPOINT specifies a command that will ALWAYS be executed when the container starts.
ENTRYPOINT ["figlet"]

# CMD specifies arguments that will be fed to the ENTRYPOINT
CMD ["Hello"]
```{{copy}}

Wait until the above updates are saved. 

Build the docker image:

> `docker build -t myimage .`

Sample output from the Docker daemon:

```
$ docker build -t myimage .
Sending build context to Docker daemon  1.547MB
Step 1/5 : FROM ubuntu:latest
 ---> d70eaf7277ea
Step 2/5 : RUN apt update
 ---> Using cache
 ---> c16803f27c9d
Step 3/5 : RUN apt install figlet
 ---> Using cache
 ---> bcfe8fc7fcd5
Step 4/5 : ENTRYPOINT ["figlet"]
 ---> Running in 46ad82e2f77d
Removing intermediate container 46ad82e2f77d
 ---> 50959c1eb417
Step 5/5 : CMD ["Hello"]
 ---> Running in 14d2a0fe2949
Removing intermediate container 14d2a0fe2949
 ---> abb5bd2c899c
Successfully built abb5bd2c899c
Successfully tagged myimage:latest
$ 
```

From the above output, the docker build process will go through the same five steps as before, but the step 2 and step 3 are using cache as we had already built some of these layers in our earlier image builds.  Since nothing had changed in these layers, Docker can simply use a cached version of the layer rather than pulling down code a second time and running those steps. 


The following command will execute `figlet hello` in the container.  Execute:

> `docker run myimage`

If arguments are provided after the image name, the specified argument will be fed to the ENTRYPOINT instead. 

The following command will execute `figlet Hello Docker!` in the container.

> `docker run myimage "Hello Docker!"`