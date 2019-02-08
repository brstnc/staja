PHP/MYSQL Platform 1.0
=======================

##### This is ***php7.3*** and ***mysql8.0.13*** server platform to develop ***PHP*** projects.
##
##
##
___
## Installation
***Step 1:*** *Cloning repository.*

```sh
git clone ssh://git@git.com.tr:10022/beyaznet/php_dev.git
```

***Step 2:*** *Get into the directory.*

```sh
cd ~/Beyaz-PHP
```

***Step 3:*** *Building docker images.*

```sh
docker-compose build
docker rmi $(docker images -q --filter "dangling=true") -f
```

***Step 4:*** *Run the docker containers.*

```sh
docker-compose up -d
```

***Step 5:*** *Enter PHP server root directory.*

```sh
cd html
```

***Step 6:*** *Edit the composer.json file and add you required php packages.*

```sh
vim composer.json
```

***Step 7:*** *Install the dependencies.*

```sh
composer install
```

***Step 8:*** *Route the domain to your container.*
> ***Find out*** your ***container IP*** on php:networks:app_net section in
`./docker-compose.yml` file.
Default IP is ***172.10.10.10***

> ***Find out*** you ***server name*** on VirtualHost/ServerName section in
`./php/sites/enabled/beyaznet-dev.conf` file.
Default server name is ***beyaznet-dev.net***

```sh
vim /etc/hosts
```
.. and add `172.10.10.10  beyaznet-dev.net`

***Step 9:*** *Congratulations! You can call your php server by typing ***beyaznet-dev.net*** on your browser.*
