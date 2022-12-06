# REDIS


### Install Redis on Ubuntu <a name="update-system"></a>
Install [page](https://github.com/phpredis/phpredis/blob/develop/INSTALL.md)

Prerequisites you need install dev package:
```shell
sudo apt install php8.1-dev -y
```
Try first:
```shell
sudo apt install redis-server -y && sudo apt install redis-tools
sudo systemctl status redis
sudo systemctl restart redis
```

If it is not full install redis, do this:
```shell
git clone https://github.com/phpredis/phpredis.git
cd phpredis
phpize
./configure [--enable-redis-igbinary] [--enable-redis-msgpack] [--enable-redis-lzf [--with-liblzf[=DIR]]] [--enable-redis-zstd]
make && make install
```
```shell
sudo nano /etc/php/8.1/cli/php.ini
extension=redis.so
```