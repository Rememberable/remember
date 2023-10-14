# PHP AND UBUNTU

### Install php

```shell
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt install php8.2 -y
```

### Install php libraries

```shell
sudo apt install php8.2-common
sudo apt install php8.2-cli
sudo apt install php8.2-fpm
sudo apt install php8.2-mysql
sudo apt install php8.2-memcache
sudo apt install php8.2-memcached -y
sudo apt install php8.2-bcmath
sudo apt install php8.2-curl
sudo apt install php8.2-mbstring -y
sudo apt install php8.2-gmp -y
sudo apt install php8.2-zip -y
sudo apt install php8.2-xml -y
sudo apt install php8.2-dev -y
sudo apt install php8.2-redis -y
sudo apt install php8.2-gd -y
sudo apt install php8.2-sqlite3
```

### Change php version

```shell
sudo update-alternatives --config php
```

### Turn on php error_log to file

```shell
cd /etc/php/8.2/cli && sudo nano /etc/php/8.2/cli/php.ini
```

1) press: f6
2) type: `;error_log = php_errors.log`
3) set directory. As example: `/home/ubuntu/logs/php_errors.log`

### Built-in web server. Run php in your browser

```shell
php -S localhost:8000
```
