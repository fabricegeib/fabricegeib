# WSL

```shell
# list of wsl install
wsl -l -v

# change default version to wsl2
wsl --set-default-version 2

# stop / restart
wsl --shutdown

#update wsl1 to wsl 2
wsl --set-version <distro name> 2
wsl --set-version Debian 2

# La conversion est en cours. Cette opération peut prendre quelques minutes...
# Pour plus d’informations sur les différences de clés avec WSL 2, visitez https://aka.ms/wsl2
# Le délai de l’opération a expiré, car aucune réponse n’a été reçue de l’ordinateur virtuel ou du conteneur.
```
## Debian 

```shell
# root
sudo su -

# chsh -s $(which bash)
```
### PM2

```shell
npm install -g pm2

pm2 startup
# To setup the Startup Script, copy/paste the following command:
# sudo env PATH=$PATH:/home/fabricegeib/.nvm/versions/node/v17.7.1/bin /home/fabricegeib/.nvm/versions/node/v17.7.1/lib/node_modules/pm2/bin/pm2 startup systemd -u fabricegeib --hp /home/fabricegeib

startup systemd -u fabricegeib --hp /home/fabricegeib

                        -------------

__/\\\\\\\\\\\\\____/\\\\____________/\\\\____/\\\\\\\\\_____
 _\/\\\/////////\\\_\/\\\\\\________/\\\\\\__/\\\///////\\\___
  _\/\\\_______\/\\\_\/\\\//\\\____/\\\//\\\_\///______\//\\\__
   _\/\\\\\\\\\\\\\/__\/\\\\///\\\/\\\/_\/\\\___________/\\\/___
    _\/\\\/////////____\/\\\__\///\\\/___\/\\\________/\\\//_____
     _\/\\\_____________\/\\\____\///_____\/\\\_____/\\\//________
      _\/\\\_____________\/\\\_____________\/\\\___/\\\/___________
       _\/\\\_____________\/\\\_____________\/\\\__/\\\\\\\\\\\\\\\_
        _\///______________\///______________\///__\///////////////__


                          Runtime Edition

        PM2 is a Production Process Manager for Node.js applications
                     with a built-in Load Balancer.

                Start and Daemonize any application:
                $ pm2 start app.js

                Load Balance 4 instances of api.js:
                $ pm2 start api.js -i 4

                Monitor in production:
                $ pm2 monitor

                Make pm2 auto-boot at server restart:
                $ pm2 startup

                To go further checkout:
                http://pm2.io/


                        -------------

[PM2] Init System found: systemd
Platform systemd
Template
[Unit]
Description=PM2 process manager
Documentation=https://pm2.keymetrics.io/
After=network.target

[Service]
Type=forking
User=fabricegeib
LimitNOFILE=infinity
LimitNPROC=infinity
LimitCORE=infinity
Environment=PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/home/fabricegeib/.nvm/versions/node/v17.7.1/bin:/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin
Environment=PM2_HOME=/home/fabricegeib/.pm2
PIDFile=/home/fabricegeib/.pm2/pm2.pid
Restart=on-failure

ExecStart=/home/fabricegeib/.nvm/versions/node/v17.7.1/lib/node_modules/pm2/bin/pm2 resurrect
ExecReload=/home/fabricegeib/.nvm/versions/node/v17.7.1/lib/node_modules/pm2/bin/pm2 reload all
ExecStop=/home/fabricegeib/.nvm/versions/node/v17.7.1/lib/node_modules/pm2/bin/pm2 kill

[Install]
WantedBy=multi-user.target

Target path
/etc/systemd/system/pm2-fabricegeib.service
Command list
[ 'systemctl enable pm2-fabricegeib' ]
[PM2] Writing init configuration in /etc/systemd/system/pm2-fabricegeib.service
[PM2] Making script booting at startup...
[PM2] [-] Executing: systemctl enable pm2-fabricegeib...
Created symlink /etc/systemd/system/multi-user.target.wants/pm2-fabricegeib.service -> /etc/systemd/system/pm2-fabricegeib.service.
[PM2] [v] Command successfully executed.
+---------------------------------------+
[PM2] Freeze a process list on reboot via:
$ pm2 save

[PM2] Remove init script via:
$ pm2 unstartup systemd

# or explicitly specify the init system
pm2 startup systems

# fabricegeib@PC-de-Fabrice:~$ pm2 startup systems
# [PM2] Init System found: systemd
# -----------------------------------------------------------
#  PM2 detected systemd but you precised systems
#  Please verify that your choice is indeed your init system
#  If you arent sure, just run : pm2 startup
# -----------------------------------------------------------
# [PM2] To setup the Startup Script, copy/paste the following command:
# sudo env PATH=$PATH:/home/fabricegeib/.nvm/versions/node/v17.7.1/bin /home/fabricegeib/.nvm/versions/node/v17.7.1/lib/node_modules/pm2/bin/pm2 startup systems -u fabricegeib --hp /home/fabricegeib

systemctl status yourService.js

# start your app

pm2 save

# fabricegeib@PC-de-Fabrice:~/iambot-discord-bot$ pm2 monit
# fabricegeib@PC-de-Fabrice:~/iambot-discord-bot$ pm2 save
# [PM2] Saving current process list...
# [PM2] Successfully saved in /home/fabricegeib/.pm2/dump.pm2

# verifiy pm2 auto start
pm2 ls
# or
pm2 status

pm2 resurrect

# disable
pm2 unstartup
# or
pm2 startup systemd
```

### Gatsby

```shell
npm install -g gatsby-cli

gatsby --version

gatsby --help

gatsby new

cd my-first-gatsby-site

# npm run develop
gatsby develop
```

```
You can now view my-first-gatsby-site in the browser.
⠀
  http://localhost:8000/
⠀
View GraphiQL, an in-browser IDE, to explore your site's data and
schema
⠀
  http://localhost:8000/___graphql
```

https://www.gatsbyjs.com/docs/tutorial/part-2/

## Ubuntu
```
Welcome to Ubuntu 20.04.4 LTS (GNU/Linux 4.4.0-19041-Microsoft x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Thu Mar 17 12:16:55 CET 2022

  System load:           0.52
  Usage of /home:        unknown
  Memory usage:          55%
  Swap usage:            0%
  Processes:             7
  Users logged in:       0
  IPv4 address for eth0: 192.168.1.47
  IPv6 address for eth0: 2a01:cb04:528:8f00:a074:7866:eb8d:2708
  IPv6 address for eth0: 2a01:cb04:528:8f00:4044:c2e4:84ea:6397
  IPv4 address for eth2: 172.26.80.1

32 updates can be applied immediately.
16 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable



This message is shown once a day. To disable it please create the
/home/fabricegeib/.hushlogin file.
```

## Ressources

https://docs.microsoft.com/fr-fr/windows/wsl/  
https://docs.microsoft.com/fr-fr/windows/wsl/compare-versions  
https://docs.microsoft.com/fr-fr/windows/wsl/install-manual  
https://docs.microsoft.com/fr-fr/windows/wsl/basic-commands  
https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-git  
https://docs.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl  
https://docs.microsoft.com/en-us/learn/modules/get-started-with-windows-subsystem-for-linux/3-integration-between-linux-and-windows  

