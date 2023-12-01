FROM ubuntu:22.04

COPY sources.list /etc/apt/sources.list

ENV DEBIAN_FRONTEND=noninteractive
ENV DEBCONF_NONINTERACTIVE_SEEN=true

RUN apt-get update && apt-get install -y xvfb fluxbox supervisor

RUN apt-get install -y python3-uinput

RUN apt-get install -y ca-certificates
RUN apt-get install -y wget

RUN wget -O "/usr/share/keyrings/xpra.asc" https://xpra.org/xpra.asc

RUN cd /etc/apt/sources.list.d ; wget https://raw.githubusercontent.com/Xpra-org/xpra/master/packaging/repos/jammy/xpra.sources

RUN apt-get update ; apt-get install -y xpra

ENV DISPLAY :99
ENV GEOMETRY 1024x768x24


WORKDIR /workspace/
ENTRYPOINT [ "/usr/bin/supervisord" ]