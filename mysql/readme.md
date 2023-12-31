# Start local MySQL

### When `docker-compose.yml` is in the root folder

```bash
docker-compose up
```

### When `docker-compose.yml` is in the nested folders

```bash
docker-compose -f ./mysql/docker-compose.yml up
```

# Access Adminer

- Go to `http://localhost:8080` to access Adminer portal.
- Enter respective credentials after selecting system as `MySQL` and hit login
- You are connected to mysql GUI and good to go now!

# Access MySQL monitor

To access MySQL monitor and execute sql queries through terminal run the following command and hit enter:

```bash
docker-compose -f mysql/docker-compose.yml run db mysql -u chai -p --host=db
```

- `-f mysql/docker-compose.yml`: points to the file which we want to run docker compose on. If we have `docker-compose.yml` in root folder we don't need to pass this flag.

- `run`: This command is used to run a one-time command for a service defined in the `docker-compose.yml` file. In this case, the service being run is named `db`

- `mysql`: This is the command that will be run within the container. In this case, it's starting the MySQL client.

- `-u chai`: Specifies the MySQL user as `chai` This is the username that will be used when connecting to the MySQL server.

- `-p`: Prompts for the MySQL user's password. **This flag indicates that the user's password will be entered interactively after running the command.**

- `--host=db`: Specifies the host where the MySQL server is running. In this case, it's set to `db`, **which is likely the name of the service defined in the `docker-compose.yml` file**.

Running this command will prompt you to enter the password. Enter `MYSQL_PASSWORD` env var value from docker compose file. And, you are good to go!

```bash
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 14
Server version: 8.1.0 MySQL Community Server - GPL

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```

# List all the databases

Run the following query to list all databases:

```bash
mysql> SHOW DATABASES;
```

Output:

```bash
mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| chaiDB             |
| information_schema |
| performance_schema |
+--------------------+
3 rows in set (0.07 sec)
```

Now, you can run mysql related commands here
