# Running the docker image

Run the docker image by executing

> `docker run myimage`

If a command is provided after the image name, the specified command will be executed instead.

What will be the output of the following command?

> * `docker run myimage figlet docker is fun`

> * `docker run myimage ls -l`

You can also launch an interactive bash shell to the created container.  Execute:

 > `docker run -it myimage bash`

Execute the following command to quit the shell.

>  `exit`