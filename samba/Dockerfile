FROM ossoleil/base

RUN apt-get -qq install samba

ADD smb.conf /etc/samba/smb.conf

RUN groupadd -g 1003 samba
RUN useradd -g 1003 -u 1003 samba

CMD /usr/sbin/smbd --daemon --foreground --log-stdout