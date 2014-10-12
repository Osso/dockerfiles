FROM base

RUN apt-get -qq install netatalk

ADD afpd.conf /etc/netatalk/afpd.conf

ADD AppleVolumes.default /etc/netatalk/AppleVolumes.default

RUN groupadd -g 1002 afpd
RUN useradd -g 1002 -u 1002 afpd

CMD /usr/sbin/afpd -d -g afpd