FROM ubuntu:16.04
MAINTAINER Alessio Deiana <adeiana@gmail.com>

RUN apt-get update && \
    apt-get -qq install samba && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD smb.conf /etc/samba/smb.conf

RUN groupadd -g 1001 samba && \
    useradd -g 1001 -u 1001 samba

CMD /usr/sbin/smbd -F --log-stdout -d=1 < /dev/null