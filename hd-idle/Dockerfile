FROM ossoleil/base

RUN apt-get -qq install debhelper
RUN apt-get -qq install wget

RUN wget http://switch.dl.sourceforge.net/sourceforge/hd-idle/hd-idle-1.05.tgz
RUN tar xvfz hd-idle-*.tgz
RUN cd hd-idle && dpkg-buildpackage -rfakeroot
RUN dpkg -i hd-idle_*.deb

CMD /usr/sbin/hd-idle -d -i 600