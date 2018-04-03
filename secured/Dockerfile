FROM ubuntu:xenial

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install wget libboost-all-dev libprotobuf-dev libssl-dev tzdata && \
    ln -fs /usr/share/zoneinfo/UTC /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata

RUN wget -O casinocoind https://github.com/casinocoin/casinocoind/releases/download/4.0.1/casinocoind-x64-ubuntu16 && \
    chmod 755 /casinocoind && \
    chown root:root /casinocoind && \
    mkdir -p /var/lib/casinocoind/db/nudb && \
    mkdir -p /var/log/casinocoind && \
    mkdir -p /etc/casinocoind && \
    mkdir -p /etc/casinocoind/cert && \
    apt remove -y wget

VOLUME /var/lib/casinocoind/

COPY config /etc/casinocoind/
COPY certificate /etc/casinocoind/cert/

EXPOSE 4443/tcp
EXPOSE 5005/tcp
EXPOSE 17771/udp

ENTRYPOINT ./casinocoind --conf=/etc/casinocoind/casinocoind.cfg
