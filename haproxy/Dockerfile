FROM haproxy:1.7
RUN curl https://github.com/gulererdinc/openshift-easy-servers2/blob/master/haproxy/haproxy.cfg --output ./haproxy.cfg 
COPY ./haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg
