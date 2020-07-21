FROM centos:7
MAINTAINER The CentOS Project <cloud-ops@centos.org>
LABEL Vendor="CentOS" \
      License=GPLv2 \
      Version=2.4.6-40

ENV ServerName=myapp 

RUN yum -y update && \
    yum -y install httpd unzip && \
    yum clean all

# Install app
COPY index.html /var/www/html/
COPY images/ /var/www/html/images/

# Config App
RUN echo "ServerName myapp.training " >> /etc/httpd/conf/httpd.conf

EXPOSE 80

ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]
