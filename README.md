# Zepplin-Spark
Dockerfile build containing installations of `ApacheSpark.v3.0.1`, `Hadoop.v3.2` , built on top of `Apache Zepplin.v.0.9.0` .


## Dockerfile: Build the Image.
- A `Dockerfile`  is a text document that contains all the commands a user could call on the command line to assemble an image. 

- The `Dockerfile` is the only file that is required to build an image.
    
- It will take about ***5minutes*** to build, depending on yor internet speed / platform you use to build the image.

- Run the following command to build the image:

```
docker build --rm --force-rm -t spark-zep . 
```

## Starting Services:

- After starting services we can then refer to our imgae under the zepplin service.

- To start the services, run the following command:

```
docker compose up --build -d
```

This command starts the services and builds the image.

To ensure the services are running, you can click on the following URL:

## Zepplin: http://localhost:8080

## Connecting to the MySQL Docker Container

- Open a fresh terminal session. From this session, you can directly connect to your mysql container using the following docker exec command:

```
docker exec -it mysql bash

```
- Your terminal prompt will change to `root@mysql:/#` when you are logged in to the container. 

- Next, you need to connect to the actual MySQL database through the mysql shell.

## Using the MySQL Shell

- From within the mysql container, you’ll use the mysql shell to authenticate your user and connect to the database.

- To connect to the database, run the following command:

```
mysql -u dataeng -p

```

>> the password for the dataeng user is in the docker-compose.yml file.

- Once you’re connected, you will see some output telling you about the MySQL version, followed by a `mysql>` command prompt. 

- This means you are ready to rock and roll!

## The Default Database

- There are two databases created by the container startup process

- There is the information_schema database and the default database. 

- You can switch to the default database since that is where you will be building your table definitions. 

The use command is how you switch database contexts.

mysql> use default;


Now you are ready to create your table definitions.