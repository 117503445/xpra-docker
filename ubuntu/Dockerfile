FROM ubuntu:22.04

COPY sources.list /etc/apt/sources.list

ENV DEBIAN_FRONTEND=noninteractive
ENV DEBCONF_NONINTERACTIVE_SEEN=true

RUN apt-get update && apt-get install -y xvfb fluxbox ca-certificates wget

# install xpra
RUN wget -O "/usr/share/keyrings/xpra.asc" https://xpra.org/xpra.asc
RUN cd /etc/apt/sources.list.d ; wget https://raw.githubusercontent.com/Xpra-org/xpra/master/packaging/repos/jammy/xpra.sources
RUN apt-get update ; apt-get install -y xpra

WORKDIR /workspace/
COPY entrypoint.sh entrypoint.sh
ENTRYPOINT ["./entrypoint.sh"]