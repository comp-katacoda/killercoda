# Exploring the WordPress container

First, show the running containers.

> `docker ps`

Launch a shell to the WordPress container by using the container name.

> `docker exec -it wordpress bash`

Check that the current folder is `/var/www/html`. 

Execute `ls` to show the files in the folder where you will find the PHP files for the application.

Execute `ps aux` to examine the processes running in the container.

Execute `printenv` to examine the environment variable. 

You will find the various environment variables (`WORDPRESS_DB_HOST`, `WORDPRESS_DB_USER`,  `WORDPRESS_DB_PASSWORD`) you have passed to the docker container. These environment variables are used by WordPress application to connect to the MySQL database.

Exit the bash shell in the wordpress container:
> `exit`