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
