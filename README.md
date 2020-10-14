# Laravel Development Guide

## # add php repository 
```
sudo add-apt-repository ppa:ondrej/php

sudo apt update

sudo apt upgrade
```
## # Install php (7.1, 7.2, 7.3 and 7.4)
```bash
sudo apt install -y php7.1 php7.1-fpm php7.1-mbstring php7.1-cli php7.1-xml php7.1-bcmath php7.1-intl php7.1-sqlite3 php7.1-zip php7.1-mysql php7.1-gd php7.1-curl php7.1-pgsql php7.1-imagick php7.1-dom

sudo apt install -y php7.2 php7.2-fpm php7.2-mbstring php7.2-cli php7.2-xml php7.2-bcmath php7.2-intl php7.2-sqlite3 php7.2-zip php7.2-mysql php7.2-gd php7.2-curl php7.2-pgsql php7.2-imagick php7.2-dom

sudo apt install -y php7.3 php7.3-fpm php7.3-mbstring php7.3-cli php7.3-xml php7.3-bcmath php7.3-intl php7.3-sqlite3 php7.3-zip php7.3-mysql php7.3-gd php7.3-curl php7.3-pgsql php7.3-imagick php7.3-dom

sudo apt install -y php7.4 php7.4-fpm php7.4-mbstring php7.4-cli php7.4-xml php7.4-bcmath php7.4-intl php7.4-sqlite3 php7.4-zip php7.4-mysql php7.4-gd php7.4-curl php7.4-pgsql php7.4-imagick php7.4-dom
```

## # Install mysql 5.7
```bash
sudo apt-get install mysql-server

sudo mysql_secure_installation
```
```
Validate Password Plugin ==> press no
Remove anonymous users? yes
Disallow root login remotely? yes
Remove test database and access to it? yes
Reload privilege tables now? yes
```
### Change mysql root password
```bash
sudo mysql -u root

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'newpassword';
EXIT;

sudo service mysql restart
```

### Install Valet For Linux
- Install OS Packages:
```bash
sudo apt-get install -y network-manager libnss3-tools jq xsel
```
- Install Valet Globally Via Composer CLI
```bash
composer global require cpriego/valet-linux
```
> Make sure to place Composer's system-wide vendor bin directory in your `$PATH`
- The `park` Command
  - Create a new directory on your machine by running something like `mkdir ~/Sites`. Next, `cd ~/Sites` and run `valet park`. This command will register your current working directory as a path that Valet should search for sites.
  - Next, create a new Laravel site within this directory: `laravel new blog`.
  - Open `http://blog.test` in your browser.



### Display PHP Info In Your Browser

```bash
mkdir ~/phpinfo && echo '<?php phpinfo();' > ~/phpinfo/index.php && cd ~/phpinfo && valet link
```
> Then go to [phpinfo.test](http://phpinfo.test) to see your current php version



### Add Valet Aliasses
```bash
curl https://raw.githubusercontent.com/ahmed-aliraqi/laravel-development-with-linux-valet/master/.bash_aliases >> ~/.bash_aliasses && source ~/.bash_aliasses
```

### Switch between php versions use the following command:

##### PHP 7.1
```bash
use-php7.1
```

##### PHP 7.2
```bash
use-php7.2
```

##### PHP 7.3
```bash
use-php7.3
```

##### PHP 7.4
```bash
use-php7.4
```
