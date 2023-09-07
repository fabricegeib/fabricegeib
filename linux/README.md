# Linux

Debian & Ubuntu

## Commands

```
# display all commands
ls /usr/bin | wc -l

# root
su -

# update & upgrade
apt update
apt upgrade

# disk status
df -h

# information
hostnamectl

ip a
```

## Cockpit

Utiliser un certificat ssl existant

```shell
sudo cp /etc/letsencrypt/live/domain_name/fullchain.pem /etc/cockpit/ws-certs.d/domain_name.cert
sudo cp /etc/letsencrypt/live/domain_name/privkey.pem /etc/cockpit/ws-certs.d/domain_name.key
```

## Docker

```
docker --version
```

## GitHub CLI

```
gh

gh repo clone user/repo .

gh repo sync
```

## MySQL

```
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

```
ssh-keygen

# for more security
ssh-keygen -t rsa -b 4096
```

Location path of your public key : `~/.ssh/id_rsa.pub`

Copy your public key on the file `~/.ssh/authorized_keys` of your distant machine

Some others options to use your public key on an other machine :

```
# first option
ssh-copy-id usert@distant_machine_IP

# second option
cat ~/.ssh/id_rsa.pub | ssh user@distant_machine_IP "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

# third option
cat ~/.ssh/id_rsa.pub
mkdir -p ~/.ssh
echo SSH_public_key >> ~/.ssh/authorized_keys
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
