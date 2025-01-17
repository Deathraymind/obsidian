- ```
  sudo apt install aptitude
  sudo aptitude install libjpeg-dev
  ```
	- nano /etc/apt/sources.list
	- deb http://ppa.launchpad.net/ondrej/php/ubuntu focal main
	  deb http://deb.debian.org/debian bullseye main contrib non-free
	  deb http://www.deb-multimedia.org bookworm main non-free
	-
	- ```bash
	  # Add "add-apt-repository" command
	  apt -y install software-properties-common curl apt-transport-https ca-certificates gnupg
	  
	  # Add additional repositories for PHP (Ubuntu 20.04 and Ubuntu 22.04)
	  LC_ALL=C.UTF-8 add-apt-repository -y ppa:ondrej/php
	  
	  # Add Redis official APT repository
	  curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg
	  echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list
	  
	  # MariaDB repo setup script (Ubuntu 20.04)
	  curl -sSL https://downloads.mariadb.com/MariaDB/mariadb_repo_setup | sudo bash
	  # Update repositories list
	  apt update
	  
	  # Install Dependencies
	  apt -y install php8.3 php8.3-{common,cli,gd,mysql,mbstring,bcmath,xml,fpm,curl,zip} mariadb-server nginx tar unzip git redis-server
	  ```
	- ```bash
	  apt install php8.3
	  ```
	- ```
	  curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
	  ```
	- ```
	  mkdir -p /var/www/pterodactyl
	  cd /var/www/pterodactyl
	  ```
	-
	- ```
	  curl -Lo panel.tar.gz https://github.com/pterodactyl/panel/releases/latest/download/panel.tar.gz
	  tar -xzvf panel.tar.gz
	  chmod -R 755 storage/* bootstrap/cache/
	  ```
	- ## [](https://pterodactyl.io/panel/1.0/getting_started.html#installation)
	- ```
	  sudo apt install mariadb-server
	  ```
	- ```
	  mariadb -u root -p
	  ```
	- mariadb
	- ```sql
	  # Remember to change 'yourPassword' below to be a unique password
	  CREATE USER 'pterodactyl'@'127.0.0.1' IDENTIFIED BY 'yourPassword';
	  CREATE DATABASE panel;
	  GRANT ALL PRIVILEGES ON panel.* TO 'pterodactyl'@'127.0.0.1' WITH GRANT OPTION;
	  exit
	  ```
	- composer update
	- ```
	  cp .env.example .env
	  ```
	- ```
	  COMPOSER_ALLOW_SUPERUSER=1 composer install --no-dev --optimize-autoloader
	  ```
	- ```
	  php artisan key:generate --force
	  ```
	- ```
	  php artisan p:environment:setup
	  ```
	- ```
	  php artisan p:environment:database
	  ```
	-
-