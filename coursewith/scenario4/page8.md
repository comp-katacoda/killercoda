# Docker Volumes (III)

Remove the `www` container.

> `docker rm -f www`{{execute}}

Check if the data stored in the volume still exist.

> `ls /var/lib/docker/volumes/web_folder/_data`{{execute}}