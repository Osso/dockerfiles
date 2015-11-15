FROM ubuntu:15.10

RUN apt-get update -qq && \
    apt-get -qq install netatalk && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN groupadd -g 1002 afpd
RUN useradd -g 1002 -u 1002 afpd

CMD ["/usr/sbin/afpd", "-d"]

EXPOSE 548

COPY afp.conf /etc/netatalk/afpd.conf
COPY AppleVolumes.default /etc/netatalk/AppleVolumes.default

