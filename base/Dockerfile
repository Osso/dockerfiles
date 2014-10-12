FROM ubuntu:14.10
MAINTAINER Alessio Deiana <adeiana@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update

RUN dpkg-reconfigure locales && \
    locale-gen en_US.UTF-8 && \
    /usr/sbin/update-locale LANG=en_US.UTF-8

ENV LC_ALL en_US.UTF-8

