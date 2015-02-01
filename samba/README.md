# Samba on Docker

## Building

1. Make sure you have the `porty/archlinux` image
1. `docker build -t porty/samba .`

## Running

To make `smbd` run on startup:

```
docker run -d --name=smbd --restart=always -v /mnt/raid:/mnt/raid -p 135:135 -p 139:139 -p 445:445 porty/samba smbd -F -S
```

To make `nmbd` run on startup:

```
docker run -d --name=nmbd --restart=always --net=host -p 137:137/udp -p 138:138/udp porty/samba nmbd -F -S
```

Note the `--net=host` parameter

## Required ports

https://www.samba.org/samba/docs/man/Samba-HOWTO-Collection/securing-samba.html#firewallports

### SMBD

* TCP 135 for ??
* TDP 139 for ??
* TCP 445 for doing the file things

### NMBD

* UDP 137 for ??
* UDP 138 for ??
