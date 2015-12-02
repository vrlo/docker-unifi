# docker-unifi
Docker build for Ubiquiti Networks' UniFi Controller.

## Volumes

* data: /var/lib/unifi
* logs: /var/log/unifi

## Running

### One-off

```shell
docker run --rm -p 8080:8080 -p 8443:8443 vrlo/docker-unifi
```

### More comprehensive

```shell
docker run \
  -p 8080:8080 -p 8443:8443 \
  -v /srv/dockerdata/unifi/data:/var/lib/unifi \
  -v /srv/dockerdata/unifi/log:/var/log/unifi \
  --name unifi \
  --restart always \
  -t vrlo/docker-unifi
```

## Notice
mongodb requires at least 3379MB available for the journal,
unless started with `--smallfiles`.
For that edit `data/system.properties` and add

```properties
unifi.db.extraargs=--smallfiles
```
