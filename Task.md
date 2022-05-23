# Steps Involved

First make a directory using the following command:

- Step 1: mkdir wp_dp

- Step 2 : Go to the directory i,e. wp_dp

Here create a docker-compose file using the following command:

```
nano/vim docker-compose.yml or .yaml (extensions)
```

- Step 3: Then write the following code:

[wp_dp.md](wp_dp.md)

- Step 4: Now From the same directory, start your Docker containers:

```
docker-compose up -d (for latest version of docker just type docker compose up -d)
```

- Step 5: To stop your WordPress application:

```
docker-compose down (for latest version of docker just type docker compose down)
```

- Step 6: There will be a folder named db_init will be created, now create the sql files named wordpress.sql and drupal.sql with the following command and code:

```
nano db_init/drupal.sql

CREATE DATABASE drupal;
CREATE USER 'drupal'@'%' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON drupal.* TO 'drupal'@'%'  WITH GRANT OPTION;
FLUSH PRIVILEGES;

nano db_init/wordpress.sql

CREATE DATABASE wordpress;
CREATE USER 'wordpress'@'%' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpress'@'%'  WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

Note: To change the root file to wheel use the following comand:

(sudo chown -R becode:wheel db_init/ to change from root)

```

- Step 7: docker compose down --volumes && docker compose up -d
