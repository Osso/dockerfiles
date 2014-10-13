FROM ossoleil/base

RUN apt-get -qq install smartmontools

ADD smartd.conf /etc/smartd.conf

CMD /usr/sbin/smartd --debug