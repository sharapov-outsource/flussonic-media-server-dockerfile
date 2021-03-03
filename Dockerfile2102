FROM ubuntu:18.04

LABEL maintainer="Sharapov A. <alexander@sharapov.biz>"

RUN apt-get -y update && \
    apt-get install -y wget python-pip && \
    wget -q -O /etc/apt/trusted.gpg.d/flussonic.gpg http://apt.flussonic.com/binary/gpg.key && \
    echo "deb http://apt.flussonic.com binary/" > /etc/apt/sources.list.d/flussonic.list && \
    apt-get -y update && \
    apt-get -y install flussonic=21.02 flussonic-transcoder curl && \
    pip install supervisor && \
    apt-get clean autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/{apt,dpkg,cache,log}/

COPY /etc/supervisord.conf /etc/supervisord.conf

ENV TERM linux

VOLUME ["/var/log/flussonic"]

EXPOSE 80 443 554 1554 1935 1443

CMD ["/usr/local/bin/supervisord"]

# HEALTHCHECK --interval=5s --timeout=5s --retries=5 CMD [ "200" = "$(curl -s -o /dev/null -w "%{http_code}" http://127.0.0.1/)" ] || exit 1
