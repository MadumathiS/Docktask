version: '3'

services:
  drupal:
    container_name: drupal
    image: drupal:latest
    ports:
      - 81:80
    volumes:
      - drupal:/var/www/html
    restart: always


  wordpress:
    container_name: wordpress
    image: wordpress
    restart: always
    ports:
      - 82:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: password
      WORDPRESS_DB_NAME: wordpress
    volumes:
      - wordpress:/var/www/html

  db:
    container_name: mysql
    image: mysql:5.7
    restart: always
    ports:
      - 3306:3306
    environment:
      MYSQL_ROOT_PASSWORD: 'root'
    volumes:
      - ./db_init:/docker-entrypoint-initdb.d
      - db:/var/lib/mysql

volumes:
  wordpress:
  drupal:
  db:


# volumes:
#   drupal_modules:
#   drupal_profiles:
#   drupal_themes:
#   drupal_sites:
#   db_data:


