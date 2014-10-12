FROM base

RUN apt-get -qq install avahi-daemon

ADD afpd.service /etc/avahi/services/afpd.service
ADD deviceinfo.service /etc/avahi/services/deviceinfo.service
ADD samba.service /etc/avahi/services/samba.service
ADD avahi-daemon.conf /etc/avahi/avahi-daemon.conf

CMD /usr/sbin/avahi-daemon