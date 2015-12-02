# docker-unifi
Docker build for Ubiquiti Networks' UniFi Controller.

## Volumes

* data: /var/lib/unifi
* logs: /var/log/unifi

## Notice
mongodb requires at least 3379MB available for the journal,
unless started with `--smallfiles`.
For that edit `data/system.properties` and add

```properties
unifi.db.extraargs=--smallfiles
```
