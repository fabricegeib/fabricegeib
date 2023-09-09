# Linux

Debian & Ubuntu

## Commands

```shell
# display all commands
ls /usr/bin | wc -l

# root
su -

# execute a command [group] without sudo
# disconnect and reconnect the [user] for the changes to take effect
sudo usermod -aG [group] [user]

# update & upgrade
apt update
apt upgrade

# disk status
df -h

# display information
hostname
hostname -i

ip a
```

## VirtualHost

```
sudo a2enmod vhost_alias
```

## Cockpit

Utiliser un certificat ssl existant

```shell
sudo cp /etc/letsencrypt/live/domain_name/fullchain.pem /etc/cockpit/ws-certs.d/domain_name.cert
sudo cp /etc/letsencrypt/live/domain_name/privkey.pem /etc/cockpit/ws-certs.d/domain_name.key
```

## DNS

```shell
show dns config

cat /etc/resolv.conf
```

## Docker

```shell
# user docker without sudo
sudo usermod -aG docker $USER

docker --version

# list containers
docker ps

# 
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container_name_or_id>

# restart with systemd
sudo systemctl restart docker

# restart docker don't use systemd (like wsl)
sudo service docker stop
sudo service docker start
sudo service docker status
```

## GitHub CLI

```shell
gh

gh repo clone user/repo .

gh repo sync
```

## MySQL

```sql
GRANT ALL PRIVILEGES ON *.* TO 'user'@localhost IDENTIFIED BY 'password';
```

## Screen

Pour lancer un script en arrière plan via une session :

```shell
screen -S session_name
./run.sh
```

Pour détacher la session `Ctrl + A` puis `d`

Rejoindre à nouveau la session

```shell
screen -r session_name
```

## SSH

```shell
ssh-keygen

# for more security
ssh-keygen -t rsa -b 4096
```

Location path of your public key : `~/.ssh/id_rsa.pub`

Copy your public key on the file `~/.ssh/authorized_keys` of your distant machine

Some others options to use your public key on an other machine :

```shell
# first option
ssh-copy-id usert@distant_machine_IP

# second option
cat ~/.ssh/id_rsa.pub | ssh user@distant_machine_IP "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

# third option
cat ~/.ssh/id_rsa.pub
mkdir -p ~/.ssh
echo SSH_public_key >> ~/.ssh/authorized_keys
```

## systemd

```shell
systemctl list-units	# Lister les services
systemctl status [nom du service].service	# Connaitre l'état d'un service
systemctl enable [nom du service].service	# Activer un service
systemctl disable [nom du service].service	# Désactiver un service
systemctl stop [nom du service].service	# Arrêter un service
systemctl start [nom du service].service	# Démarrer un service
systemctl restart [nom du service].service	# Redémarrer un service
systemctl reload [nom du service].service	# Recharge du service avec les nouveaux paramètres (évite les coupures)
systemctl daemon-reload	# Pour prendre en compte la modification d'un service
```

## Transmission

Copy the certificate

```shell
mkdir -p /etc/transmission-daemon/ssl
sudo cp /etc/letsencrypt/live/domain_name/fullchain.pem /etc/transmission-daemon/ssl/transmission.crt
sudo cp /etc/letsencrypt/live/domain_name/privkey.pem /etc/transmission-daemon/ssl/transmission.key
```

Edit the config of transmission :

```shell
sudo nano /etc/transmission-daemon/settings.json
```

Edit these lines :

```json
"rpc-ssl": true,
"rpc-ssl-verify": true,
"rpc-certificate": "/etc/transmission-daemon/ssl/transmission.crt",
"rpc-key": "/etc/transmission-daemon/ssl/transmission.key",
```

```shell
sudo systemctl restart transmission-daemon
```
