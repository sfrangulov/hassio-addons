FROM influxdb:1.5.2

RUN apt-get update \
 && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    		jq \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* ~/.cache

COPY influxdb.conf /etc/influxdb/influxdb.conf

COPY run_addon.sh /
RUN chmod a+x /run_addon.sh

EXPOSE 8086
ENTRYPOINT [ "/run_addon.sh" ]
CMD ["influxd"]
