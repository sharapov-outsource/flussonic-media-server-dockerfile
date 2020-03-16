## Flussonic Media Server Docker Container based on Ubuntu 18.04

#### How to use?

```bash
git clone git@github.com:sharapov-outsource/flussonic-media-server-dockerfile.git mediasrv
cd mediasrv
cp etc/flussonic/flussonic.conf_sample etc/flussonic/flussonic.conf
cp etc/flussonic/license.txt_sample etc/flussonic/license.txt
docker-compose up -d
```

#### Flussonic UI

```bash
http://127.0.0.1:8122/
```

There you need to put your license key before using

#### Login to docker container

```bash
docker exec -it flussonic_container /bin/bash
```

#### Which version is currently installed?
```bash
docker exec -it flussonic_container dpkg -l | grep flussonic
```

