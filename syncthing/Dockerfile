FROM ossoleil/base

RUN apt-get -qq install software-properties-common

# Add the release PGP keys:
RUN curl -s https://syncthing.net/release-key.txt | apt-key add -

# Add the "release" channel to your APT sources:
RUN echo "deb http://apt.syncthing.net/ syncthing release" >> /etc/apt/sources.list

RUN apt-get update
RUN apt-get -qq install syncthing

ENV STGUIADDRESS http://0.0.0.0:8090
EXPOSE 8090

RUN groupadd -g 1001 syncthing
RUN useradd -g 1001 -u 1001 syncthing

USER syncthing
VOLUME /home/syncthing
CMD /usr/bin/syncthing -no-browser