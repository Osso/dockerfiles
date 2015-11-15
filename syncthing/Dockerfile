FROM ubuntu:15.10
MAINTAINER Alessio Deiana <adeiana@gmail.com>

RUN apt-get update && \
    apt-get install -y curl && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Add the release PGP keys:
RUN curl -s https://syncthing.net/release-key.txt | apt-key add -

# Add the "release" channel to your APT sources:
RUN echo "deb http://apt.syncthing.net/ syncthing release" >> /etc/apt/sources.list

RUN apt-get update && \
    apt-get -qq install software-properties-common curl syncthing && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV STGUIADDRESS http://0.0.0.0:8090
EXPOSE 8090

RUN groupadd -g 1001 syncthing
RUN useradd -g 1001 -u 1001 syncthing

USER syncthing
VOLUME /home/syncthing
CMD /usr/bin/syncthing -no-browser