# Mac OS

## Apache 2

```shell
sudo apachectl stop
sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist 2>/dev/null

brew install httpd

brew services start httpd
http://localhost:8080

ps -aef | grep httpd
brew services restart httpd

tail -f /opt/homebrew/var/log/httpd/error_log

brew services stop httpd
brew services start httpd
brew services restart httpd

/opt/homebrew/etc/httpd/httpd.conf

/opt/homebrew/var/www

DocumentRoot "/opt/homebrew/var/www"
<Directory "/Users/your_user/Sites">

LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so
```

## visual studio code

```shell
brew install --cask visual-studio-code
```

## phpmyadmin

```shell
brew install phpmyadmin
```

```shell
brew tap shivammathur/php
# brew install php@7.4
brew install shivammathur/php/php@7.4

# Switch version
brew unlink php
brew link php@7.4 --force

brew list | grep php
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

## updates

```shell
sudo rm -rf /Library/Developer/CommandLineTools
sudo xcode-select --install
```
