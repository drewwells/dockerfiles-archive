FROM debian:stretch
MAINTAINER Drew Wells <drew.wells00@gmail.com>

RUN mkdir -p /var/run/sshd
RUN apt-get update && \
    apt-get install -y openconnect openssh-server netcat-traditional \
    ocproxy dnsutils telnet python3-pip curl iptables net-tools && \
    apt-get clean && \
    rm -rf /var/cache/apt/* && \
    rm -rf /var/lib/apt/lists/*

COPY run.sh /run.sh
RUN chmod 0755 /run.sh

ENTRYPOINT ["/run.sh"]
