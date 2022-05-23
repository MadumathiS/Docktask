# Docktask
# The mission


This challenge will have you explore both the docker (CLI and Dockerfiles) and docker-compose command. The challenge is going to be divided into two sections, one where you'll explore the tool and another where you'll apply what you've learned in a practical example.

Follow the instructions below to get started on the first part:

- Install docker on your machine, then follow a tutorial (requires an account). Make sure you understand the CLI usage as well as how to create your own images with Dockerfiles.
- Install docker-compose on your machine, then follow a tutorial.
- Practice by containerizing websites, applications and services you already deployed in the past like the COGIP or a git server. You can also deploy new ones, for example coming from this list. Do this until you feel confortable with both docker and docker-compose.

Often times you will have to deploy multiples websites on the same server. Using containers makes that process easy and allows for high availability.
Your mission will be to deploy both a Wordpress and a Drupal website using the following architecture:

- a mysql database containing a tables for both websites
- a wordpress container
- a drupal container
- a reverse proxy container

Follow the instructions below to guide you along.

- Check how to install Wordpress and Drupal locally and understand how it works
- Try to run both website individually in docker containers with volume mapping and port redirection. Try to access it on your localhost to ensure that everything is working
- Once you understand how it works individually, try to make a docker-compose file allowing to deploy the full stack. The following services are expected: Wordpress, Drupal, a database and a webserver.
- Configure your webserver to act as a reverse proxy. You should be able to access both websites from different URLs in your local environment (subdomain or subfolder)
- When you are done, comment on the issue linked to this challenge on your training's repository.

```
NOTE: A good "rule of thumb" when it comes to containerization is that each process should live in its own container.
 As an example, an Apache + PHP + MySQL website should have at least two (depends if you consider PHP has its own service) or even three containers (one for each services) talking to each other for the required data to work.
```
