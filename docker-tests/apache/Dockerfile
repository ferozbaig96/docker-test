# EXPOSE directive
# exposes container port to a local host port
## START
FROM centos:latest
MAINTAINER abc <abc@example.com>
RUN yum update -y && yum install -y httpd
RUN echo "HELLO" > /var/www/html/index.html
# exposing conatiner port 80
EXPOSE 80
# start apache on container instantiation
ENTRYPOINT apachectl "-DFOREGROUND"
