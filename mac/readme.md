# Mac OS

```shell
brew install phpmyadmin
```

return :

```
To enable phpMyAdmin in Apache, add the following to httpd.conf and
restart Apache:
    Alias /phpmyadmin /usr/local/share/phpmyadmin
    <Directory /usr/local/share/phpmyadmin/>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        <IfModule mod_authz_core.c>
            Require all granted
        </IfModule>
        <IfModule !mod_authz_core.c>
            Order allow,deny
            Allow from all
        </IfModule>
    </Directory>
Then open http://localhost/phpmyadmin
The configuration file is /usr/local/etc/phpmyadmin.config.inc.php
==> Summary
🍺  /usr/local/Cellar/phpmyadmin/5.2.0: 3,553 files, 44.7MB
==> Running `brew cleanup phpmyadmin`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`)
```
