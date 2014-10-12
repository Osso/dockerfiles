FROM base

RUN apt-get -qq install avahi-daemon

ADD afp.service /etc/avahi/services/afp.service
ADD samba.service /etc/avahi/services/samba.service
ADD sftp.service /etc/avahi/services/sftp.service
ADD ssh.service /etc/avahi/services/ssh.service
ADD avahi-daemon.conf /etc/avahi/avahi-daemon.conf

CMD /usr/sbin/avahi-daemon