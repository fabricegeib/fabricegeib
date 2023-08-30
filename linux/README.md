# Linux

## Cockpit

Utiliser un certificat ssl existant

```
sudo cp /etc/letsencrypt/live/[domain]/fullchain.pem /etc/cockpit/ws-certs.d/[domain].cert
sudo cp /etc/letsencrypt/live/[domain]/privkey.pem /etc/cockpit/ws-certs.d/[domain].key
```
