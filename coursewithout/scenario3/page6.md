# Customizing the Nginx website 

You should perform the following steps in <b>Tab 2</b> (while the nginx server should be running in <b>Tab 1</b>). 

The default webpage at the root folder is located at `/usr/share/nginx/html/index.html` in the Nginx container. 
- You may execute `cat /usr/share/nginx/html` in the nginx container to show the HTML source of the default webpage. 
- You can also show the content of the file in the Docker host by executing the command `docker execute  [nginx's container ID] cat /usr/share/nginx/html/index.html`.

Execute the command:
`cat /usr/share/nginx/html/index.html` in the container `c0` to view the source code of the `index.html` file.

> `docker exec -it c0 cat /usr/share/nginx/html/index.html`

We will customize the webpage shown when Nginx web server is accessed.

# Create the customized webpage

First, create a webpage `index.html` in Docker host with the following content.

```
This is my first website
```

You can either use your favourite editor (e.g. nano, vi) or create the file using the following command.

> `echo 'This is my first website' > index.html`

# Copy files to/from Docker container

The `docker cp` commands can be used to copy files to/from the container. 
- To copy files from the Docker host to the container, execute `docker cp [source file] [container ID]:[destination path]`.
- E.g. To copy the customized `index.html` from the Docker host into the container, we may execute  `docker cp index.html [nginx container ID]:/usr/share/nginx/html`.

Execute the following command in <b>Tab 2</b>:

> `docker cp index.html c0:/usr/share/nginx/html`

Verify that the default webpage is updated. Execute:

> `curl localhost:20080`

Visit `http://localhost:20080` in your browser (if you are running the lab in your own computer).

In Killercoda, you may visit the port by clicking the top-right menu and choose Traffic / Ports. Type in 20080 to custom ports and click Access.
 
# Clean up the containers

Switch to <b>Tab 1</b>, stop the Nginx server with Ctrl+C.

Use the following command to clean up all stopped containers.

> `docker container prune`

Click 'Y' to confirm.