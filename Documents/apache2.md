# Apache

https://httpd.apache.org/

```shell
httpd -v

sudo apachectl start

sudo apachectl stop

sudo apachectl restart
```

http://localhost

## Document Root

Default folder : `/Library/WebServer/Documents`

`/etc/apache2/`

## Install Apache with Brew

```shell
sudo apachectl stop
sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist

brew install httpd

sudo brew services start httpd
```

`/usr/local/etc/httpd/httpd.conf`

## Create VirtualHost

Create a virtualHost for the application Cockpit

```shell
sudo nano /etc/apache2/sites-available/cockpit.conf
```

Inside `cockpit.conf` insert :

```apacheconf
<VirtualHost *:80>
    ServerName nomdedomaine
    Redirect / https://nomdedomaine/
</VirtualHost>

<VirtualHost *:443>
    ServerName nomdedomaine
    DocumentRoot /var/www/html  # Répertoire racine de votre site, ajustez selon vos besoins
    SSLEngine on
    SSLCertificateFile /etc/letsencrypt/live/nomdedomaine/fullchain.pem
    SSLCertificateKeyFile /etc/letsencrypt/live/nomdedomaine/privkey.pem
</VirtualHost>
```

Enable the VirtualHost

```shell
sudo a2ensite cockpit.conf
```

Restart Apache2

```shell
sudo systemctl restart apache2
```

## Backup

sudo cp -r /etc/apache2 /backup/apache2

or

sudo rsync -av /etc/apache2 /backup/apache2
