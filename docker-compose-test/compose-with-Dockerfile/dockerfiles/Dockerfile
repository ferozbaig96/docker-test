FROM centos:latest
RUN yum install httpd -y && \
	echo "HELLO" > /var/www/html/index.html
ENTRYPOINT apachectl "-DFOREGROUND"
