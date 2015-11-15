FROM ubuntu:15.10
MAINTAINER Alessio Deiana <adeiana@gmail.com>

RUN apt-get update && \
    apt-get -qq install smartmontools ssmtp && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD smartd.conf /etc/smartd.conf
ADD ssmtp.conf /etc/ssmtp/ssmtp.conf

CMD /usr/sbin/smartd --debug