# TP IoT - Configuration mTLS MQTT
**Date :** 28 Mars 2026
**Objectif :** Mise en place d'une authentification mutuelle (mTLS) pour sécuriser un broker Mosquitto.

## Contenu du dépôt
* `ca.crt` : Certificat de l'Autorité de Certification (Root).
* `broker.crt` : Certificat du serveur MQTT signé par la CA.
* `client.crt` : Certificat du client IoT signé par la CA.
* `mosquitto-mtls.conf` : Fichier de configuration sécurisé pour Mosquitto.

## Sécurité
> [!IMPORTANT]
> Les clés privées (`.key`) sont exclues de ce dépôt via `.gitignore` pour respecter les bonnes pratiques de sécurité.

## Test de connexion
```bash
mosquitto_pub -h localhost -p 8883 --cafile ca.crt --cert client.crt --key client.key -t "test/secured" -m "mTLS OK"
```
