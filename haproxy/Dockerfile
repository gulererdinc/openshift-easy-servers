FROM haproxy:1.7
RUN wget https://github.com/gulererdinc/openshift-easy-servers/blob/master/haproxy/haproxy.cfg ./
COPY ./haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg
