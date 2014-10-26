FROM ossoleil/base

RUN apt-get -qq install smartmontools ssmtp

ADD smartd.conf /etc/smartd.conf
ADD ssmtp.conf /etc/ssmtp/ssmtp.conf

CMD /usr/sbin/smartd --debug