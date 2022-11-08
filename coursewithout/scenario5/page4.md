# Exploring the MySQL Server container

Start a bash shell into the msyql container

> `docker exec -it mysql bash`

Login to the mysql database server using the `wordpress` account.

> `mysql -u wordpress -p`

Input `12345` as password.

To show the databases, execute:

> `show databases;`

Change to the `wordpress` database. Execute:

> `use wordpress;`

To list all the tables, execute:

> `show full tables;`

**\*Note\***: You should first complete the installation of wordpress in the previous step to view the wordpress tables.

To describe and get data from the `wp_posts` table, execute:

> `describe wp_posts;`

> `select ID, post_title, post_author, post_date from wp_posts;`

Exit the mysql client.

> `exit`

Exit the `mysql` container.

> `exit`