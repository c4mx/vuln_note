FROM nginx:latest

COPY default.conf /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /extdisks
COPY nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /tmp/syslogbackup
RUN echo "file in /tmp/syslogbackup/" > /tmp/syslogbackup/test.html

RUN mkdir -p /tmp/test1/test2
RUN echo "file in /tmp/test1/" > /tmp/test1/test.html
RUN echo "file in /tmp/test1/test2/" > /tmp/test1/test2/test.html
