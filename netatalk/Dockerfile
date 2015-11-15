FROM ubuntu:15.10

RUN apt-get update -qq && \
    apt-get -qq install wget build-essential libevent-dev libssl-dev \
        libgcrypt-dev libkrb5-dev libpam0g-dev libwrap0-dev libdb-dev \
        libtdb-dev libmysqlclient-dev avahi-daemon libavahi-client-dev \
        libacl1-dev libldap2-dev libcrack2-dev systemtap-sdt-dev \
        libdbus-1-dev libdbus-glib-1-dev libglib2.0-dev tracker \
        libtracker-sparql-1.0-dev libtracker-miner-1.0-dev && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN wget http://sourceforge.net/projects/netatalk/files/netatalk/3.1.7/netatalk-3.1.7.tar.gz

RUN tar vxzf netatalk-3.1.7.tar.gz && \
    cd netatalk-3.1.7 && \
    ./configure \
        --with-init-style=debian-systemd \
        --without-tdb \
        --with-cracklib \
        --with-pam-confdir=/etc/pam.d \
        --with-dbus-sysconf-dir=/etc/dbus-1/system.d \
        --with-tracker-pkgconfig-version=1.0 && \
    make && \
    make install

RUN groupadd -g 1002 afpd
RUN useradd -g 1002 -u 1002 afpd

COPY afp.conf /usr/local/etc/afp.conf

CMD ["/usr/local/sbin/afpd", "-d"]

EXPOSE 548

