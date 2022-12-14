# Overview of Dockerfile
Dockerfile is a text file that contains all the commands, in order, needed to build a given image. 

Create a file named "DockerFile" as follows:

```
# Use the latest debian linux image as a parent image
FROM ubuntu:latest

# install figma using the apt package manager
RUN apt update 
RUN apt install figlet

# Run the command figlet "hello" when the container is launched
CMD ["figlet", "Hello"]
```{{copy}}

About the Dockerfile instructions:
* **FROM:** specifies the base image to use as the starting point for this new image you're creatin
* **RUN:** lets you execute commands inside  your Docker image. The command executs once at build time and get written into your Docker image as a new layer.
* **CMD:** lets you define a default command to run when your container starts. E.g. start your web application’s app server when the image is run (only one CMD command in the DockerFile).

You may visit the Dockerfile reference page at https://docs.docker.com/engine/reference/builder to understand more about the various commands for Dockerfiles.

Wait until the above updates are saved. 