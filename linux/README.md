# Linux

## Cockpit

Utiliser un certificat ssl existant

```
sudo cp /etc/letsencrypt/live/domain_name/fullchain.pem /etc/cockpit/ws-certs.d/domain_name.cert
sudo cp /etc/letsencrypt/live/domain_name/privkey.pem /etc/cockpit/ws-certs.d/domain_name.key
```

## Screen

Pour lancer un script en arrière plan via une session :

```
screen -S session_name
./run.sh
```

Pour détacher la session `Ctrl + A` puis `d`

Rejoindre à nouveau la session

```
screen -r session_name
```
