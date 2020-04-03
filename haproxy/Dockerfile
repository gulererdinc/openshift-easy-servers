FROM debian:9-slim

# base packages, core clients
RUN apt-get -y update && \
    apt-get -y install haproxy net-tools procps
     
#RUN mkdir -p /var/run/haproxy

# cleaning
RUN apt-get -y autoclean && \
    apt-get -y --purge autoremove && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/*

EXPOSE 443
CMD ["/usr/sbin/haproxy","-D","-f","/etc/haproxy/haproxy2.cfg","-p","/var/run/haproxy/haproxy.pid"]
