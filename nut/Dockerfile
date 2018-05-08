ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

RUN echo "http://nl.alpinelinux.org/alpine/edge/main/" >> /etc/apk/repositories
RUN echo "http://nl.alpinelinux.org/alpine/edge/testing/" >> /etc/apk/repositories
RUN apk add nut jq --update-cache

RUN mkdir /var/run/nut
RUN chown root:nut /var/run/nut
RUN chmod 770 /var/run/nut

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
