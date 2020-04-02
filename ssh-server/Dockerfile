FROM debian:9-slim

# base packages, core clients
RUN apt-get -y update && \
    apt-get -y install openssh-server net-tools
     
RUN mkdir -p /var/run/sshd

# authorized_keys for root
RUN useradd autom8
mkdir /home/autom8/.ssh && \
echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCsqcGFeAedSf3PMKFSnVM8dpsF3yZ2hU3F9Klr7FQ6v5uQEyhbJpzX7pvahBiHpHeK+GpDRcRdxiXpUSbTr/VvEiC/thtl9wMFtd/NhZCD9GOjlNF1S26Lc6fz0l2Gh6mDd0mXiUSaKh8ZDg0N8ie32kEaxj9YK6K0sIjf51iA4NrPrqH2kS9v5fTqvcavli4CPCDp9wYukSCn82AYeQTaCe/dNiqog6v5y4M8EfFcyfU+INoW8e1bV5D+ITg+UpK86EQpSFOl8Nm2Qs+VU7DwAAzgLJ42h9zEFQikPPOmzrsOT6Zza4/hmuFuNvP+21t9domn4lGlqqlsIo3zgPgN' > /root/.ssh/authorized_keys

RUN chown -R autom8.autom8 /home/autom8/.ssh && \
    chmod -R a-rwx,u=rwX,g=,o= /home/autom8/.ssh

# cleaning
RUN apt-get -y autoclean && \
    apt-get -y --purge autoremove && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/*

EXPOSE 7722
CMD ["/usr/sbin/sshd","-D","-p","7722"]
