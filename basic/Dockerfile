FROM ubuntu:xenial

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install python-software-properties curl git scons ctags cmake pkg-config protobuf-compiler libprotobuf-dev libssl-dev python-software-properties libboost-all-dev tzdata software-properties-common && \
    ln -fs /usr/share/zoneinfo/UTC /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata

RUN git clone https://github.com/casinocoin/casinocoind.git src; cd src/; git checkout master

RUN cd src/; scons && \
    cp build/casinocoind /casinocoind; strip /casinocoind && \
    mkdir -p /var/lib/casinocoind/db/nudb && \
    mkdir -p /var/log/casinocoind && \
    mkdir -p /etc/casinocoind

VOLUME /var/lib/casinocoind/

COPY config /etc/casinocoind/

RUN rm -r src

EXPOSE 4443/tcp
EXPOSE 5005/tcp
EXPOSE 17771/udp

ENTRYPOINT ./casinocoind --conf=/etc/casinocoind/casinocoind.cfg
