# Dockerfile based on latest centos for Apache server
FROM centos:latest
MAINTAINER abc abc@example.com
RUN yum update -y && yum install -y \
	telnet \
	httpd
WORKDIR /var/www/html/
RUN echo "HELLO 1" > /index.html
EXPOSE 80
# start apache on container instantiation
ENTRYPOINT apachectl "-DFOREGROUND"
#RUN useradd -ms /bin/bash httpduser
#USER httpduser
