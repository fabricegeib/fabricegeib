# wordpress

## wp-cli

Install CLI

```
curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar

php wp-cli.phar --info

chmod +x wp-cli.phar
sudo mv wp-cli.phar /usr/local/bin/wp

wp --info

wp cli update
```

Create and configure a new WordPress

```
wp core download
wp config create --dbhost=host.db --dbname=prefix_db --dbuser=username --prompt=dbpass --dbprefix='wp_' --dbcharset='utf8' --dbcollate=''
chmod 600 wp-config.php

# configure wp-config.php
wp core install --url=yourwebsite.com --title="Your Blog Title" --admin_name=wordpress_admin --admin_password=4Long&Strong1 --admin_email=you@example.com

wp core install --url=wpclidemo.dev --title="WP-CLI" --admin_user=wpcli --admin_password=wpcli --admin_email=info@wp-cli.org

wp db create

# enable file uploads
cd wp-content
mkdir uploads
chgrp web uploads/
chmod 775 uploads/

# clear command history
history -c && exit

wp package install wp-cli/admin-command

wp maintenance-mode activate
wp maintenance-mode status
```

```
wp --info

# return
OS:     Linux 5.10.0-25-cloud-amd64 #1 SMP Debian 5.10.191-1 (2023-08-16) x86_64
Shell:  /bin/bash
PHP binary:     /usr/bin/php7.4
PHP version:    7.4.33
php.ini used:   /etc/php/7.4/cli/php.ini
MySQL binary:   /usr/bin/mysql
MySQL version:  mysql  Ver 15.1 Distrib 10.5.19-MariaDB, for debian-linux-gnu (x86_64) using  EditLine wrapper
SQL modes:
WP-CLI root dir:        phar://wp-cli.phar/vendor/wp-cli/wp-cli
WP-CLI vendor dir:      phar://wp-cli.phar/vendor
WP_CLI phar path:       /home/fabricegeib
WP-CLI packages dir:
WP-CLI cache dir:       /home/fabricegeib/.wp-cli/cache
WP-CLI global config:
WP-CLI project config:
WP-CLI version: 2.8.1
```

## resources

- https://developer.wordpress.org/cli/commands/admin/
- https://make.wordpress.org/cli/handbook/guides/quick-start/
