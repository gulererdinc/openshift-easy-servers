FROM fedora:latest

RUN dnf -y install openssh-server

# setup openssh
RUN sed -i "s/#PasswordAuthentication yes/PasswordAuthentication no/" /etc/ssh/sshd_config
RUN mkdir /var/run/sshd
RUN rm -f /var/run/nologin

EXPOSE 7722

CMD ["/usr/sbin/sshd","-D","-p","7722"]
