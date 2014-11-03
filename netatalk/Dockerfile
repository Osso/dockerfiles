FROM ubuntu:14.04

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys AC857259

RUN echo "deb http://ppa.launchpad.net/ali-asad-lotia/netatalk-stable/ubuntu $(lsb_release -cs) main" \
       > /etc/apt/sources.list.d/launchpad-ali-asad-lotia-netatalk.list

RUN apt-get update -qq

RUN apt-get -qq install netatalk

ADD afp.conf /etc/netatalk/afp.conf

RUN groupadd -g 1002 afpd
RUN useradd -g 1002 -u 1002 afpd

CMD /usr/sbin/afpd -d

EXPOSE 548

