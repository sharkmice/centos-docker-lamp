# centos-lamp
A CentOS 7 Docker LAMP suitable for local Drupal or WordPress development. This is meant to simulate a development environment compatible with cPanel hosting. This container is ideal for running on Windows or Mac as everything is in one container.

# Features
- Centos 7
- Apache 2.4
- Mod SSL
- MariaDB 10.1
- PHP 5.6
- SSH
- phpMyAdmin
- Git
- Drush
- NodeJS

# Example Usage with Data in Container

Build and then run this container with: 

``docker run -d -p 8080:80 -p 8443:443 -p 8220:22-t otherdata/centos-lamp``

To access the web server visit https://localhost:8443, or http://localhost:8080

To access phpMyadmin visit https://localhost:8080/phpmyadmin. 

Attach to the container by running `sudo docker exec -i -t da94d0ba7f7c /bin/bash`

Put your web code in /var/www/html/

# Example Usage for Existing Web Project

Create a project folder and database folder.

`mkdir -p project/database`
`mkdir -p project/html`

Move into the project folder.

`cd project`

Run the command to launch the docker and map project and database directory.

``docker run -d -p 8080:80 -p 8443:443 -p 8022:22 -v `pwd`/html:/var/www/html -v `pwd`/database:/var/lib/phpMyAdmin/upload -t otherdata/centos-lamp``

You can now move a copy of your Drupal or WordPress files into the html folder, and move an .sql dump into the database folder (Or upload it using phpMyAdmin). 

To access the web server visit https://localhost:8443, or http://localhost:8080

To access phpMyadmin visit https://localhost:8080/phpmyadmin.   
