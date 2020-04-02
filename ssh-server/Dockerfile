FROM debian:9-slim

# base packages, core clients
RUN apt-get -y update && \
    apt-get -y install openssh-server net-tools
     
RUN mkdir -p /var/run/sshd

# authorized_keys for root
COPY .ssh/ /root/.ssh/
RUN chown -R root.root /root/.ssh && \
    chmod -R a-rwx,u=rwX,g=,o= /root/.ssh

# cleaning
RUN apt-get -y autoclean && \
    apt-get -y --purge autoremove && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/*

EXPOSE 22
CMD ["/usr/sbin/sshd","-D","-p","22"]
