FROM ubuntu:15.10
MAINTAINER Alessio Deiana <adeiana@gmail.com>

RUN apt-get -y update && \
    apt-get -y install htop git telnet nano mailutils && \
    apt-get -y install mytop sysstat ncdu && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

CMD /bin/bash