# Pushing image to Docker hub.

Open an account in [docker hub](https://hub.docker.com/) if you have not done so before.

Before the image can be pushed to your docker hub repository, 
tag your docker image in the format of <your repository name in dockerhub>/<your image name>.

Execute (replace <repository name> with your Docker hub's repository name):

`docker tag myimage <repository name>/myimage`{{copy}}

Execute:

> `docker login`

Input your username and password to login to Docker hub.

Execute: 

> `docker push <your repository name in dockerhub>/myimage`{{copy}}

Visit Docker hub in browser and check that the image is pushed to your repository.

After the image is pushed successfully, it can be pulled from any computer by executing:

> `docker pull <your Docker Hub's repository name>/myimage`{{copy}}