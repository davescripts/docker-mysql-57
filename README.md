# Docker Container: MySQL 5.7

Dockerfile for a Container with MySQL 5.7.

The Dockerfile, and the shell scripts, have been copied from MySQL GitHub repository, specifically from the following folder: [https://github.com/mysql/mysql-docker/tree/mysql-server/5.7](https://github.com/mysql/mysql-docker/tree/mysql-server/5.7)

<br>

## Build

Create Docker Image.

```sh
docker build -t <image_name> .
```

_Replace **&lt;image_name&gt;** with the name you want for the image._

<br>

Example.

```sh
docker build -t image_mysql57  .
```

<br>

## Run

Create Docker Container.

```sh
docker run -d -p 3306:3306 --name=<container_name> -e MYSQL_ROOT_PASSWORD=<pwd> -e MYSQL_ROOT_HOST=% \
<image_name>
```

_Replace **&lt;container_name&gt;** with the name you want for the container,<br>
**&lt;pwd&gt;** with the password for your root user, and<br>
**&lt;image_name&gt;** with the name of the image you specified on the Build command above._

<br>

Example.

```sh
docker run -d -p 3306:3306 --name=container_mysql57 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_ROOT_HOST=% \
image_mysql57
```


<br>

## Test

If you have telnet installed on your machine, you can perform a quick test by executing the following command:

```sh
telnet localhost 3306
```
