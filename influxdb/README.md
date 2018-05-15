# InfluxDB server for hass.io

Idea from https://github.com/bestlibre/hassio-addons/tree/master/influxdb

## Description

This addon provide an influxdb database to [store data from homeassistant](https://home-assistant.io/components/influxdb/) and/or use it for [data retrieval](https://home-assistant.io/components/sensor.influxdb/).

This a wrapper around the [official influxdb image](https://hub.docker.com/_/influxdb/).

The data are stored in the addon /data volume. You can create a backup with the `influxd`command. See the documentation [here](https://docs.influxdata.com/influxdb/v1.2/administration/backup_and_restore/) and especialy the [remote backups section](https://docs.influxdata.com/influxdb/v1.2/administration/backup_and_restore/#remote-backups).

To create the database on first run, you can use the [http api](https://docs.influxdata.com/influxdb/v1.3/guides/writing_data/) :
```
curl -i -XPOST http://hassio.local:8086/query --data-urlencode "q=CREATE DATABASE home_assistant"
```
If this doesn't work, try to replace ̀hassio.local` with your hassio IP.
