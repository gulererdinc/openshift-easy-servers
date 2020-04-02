FROM debian:9-slim

# base packages, core clients
RUN apt-get -y update && \
    apt-get -y install haproxy net-tools
     
RUN mkdir -p /var/run/haproxy

# cleaning
RUN apt-get -y autoclean && \
    apt-get -y --purge autoremove && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/*

EXPOSE 443
CMD ["/usr/sbin/haproxy","-Ws","-f","/etc/haproxy/haproxy.cfg"]
