# anberra/grafana-arm32v7
Grafana installed in a balenalib/rpi-raspbian stretch for arm32v7 (tested in RPI3)

# Description
It is ready to run in a Raspberry Pi, tested in RPI3.

# Usage
It is recommended to add persistence to the container, for both the database and other stuff (grafana-lib) and the configuration file (grafana-conf):
```
docker volume create grafana-lib
docker volume create grafana-conf
```
To launch the container:
```
docker run \
  -d \
  -p 3000:3000 \
  --name=grafana \
  --mount type=volume,source=grafana-lib,destination=/var/lib/grafana \
  --mount type=volume,source=grafana-conf,destination=/etc/grafana \
  anberra/grafana-arm32v7
```
