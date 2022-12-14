# Inspecting the Docker Image

**Task 1**

Use the `docker inspect` command to examine the details about the docker image including
* the layers in the image 
* the driver used to store the layers
* the architecture / OS it has been created for
* ...

Execute:

> `docker image inspect myimage`{{execute}}

As the image information is displayed in JSON format, we can  use the inspect command with some filtering info to just get specific data from the image. E.g. to get the layers in the docker image,  execute:

> `docker image inspect --format "{{json .RootFS.Layers}}" myimage | jq`{{execute}}

Sample output:

```
$ docker image inspect --format "{{json .RootFS.Layers}}" myimage | jq
[
  "sha256:47dde53750b4a8ed24acebe52cf31ad131e73a9611048fc2f92c9b6274ab4bf3",
  "sha256:0c2689e3f9206b1c4adfb16a1976d25bd270755e734588409b31ef29e3e756d6",
  "sha256:cc9d18e90faad04bc3893cfaa50b7846ee75f48f5b8377a213fa52af2189095c",
  "sha256:fd5b2f8886cb277036303c9db606d09a68e906dc933bae7b88b07b8e2b6129f1",
  "sha256:a34eb36f9cabde040fdaf94631c13eee196cac40c959d0c08093296554e38305"
]
```


When compared with the layers in the Ubuntu base image, Which layers are common between the two images?

> `apt install jq`{{exec}}

> `docker image inspect --format "{{json .RootFS.Layers}}" ubuntu | jq`{{execute}}

**Task 2**

Examine the layers of `myimage` and  the Ubuntu base image.

> `docker image history myimage`{{execute}}

> `docker image history ubuntu`{{execute}}

* What are the common layers between the two docker images? 
* What is the size of the additional layers for `myimage`?
* What is the default command in the ubuntu image?