#Dockerfile for Cart Frontend
#DOCKERKEYWORD options
FROM index.docker.io/centos:7
MAINTAINER mohanraz@gmail.com
RUN yum -y update
ADD scripts /opt
RUN chmod 755 /opt/installapachephp.sh
RUN /opt/installapachephp.sh
ADD code /var/www/html
ENV MY_DB_HOST_WRITE=test
RUN ln -sf /proc/self/fd/1 /var/log/httpd/access_log
RUN ln -sf /proc/self/fd/2 /var/log/httpd/error_log
EXPOSE 80
CMD ["httpd", "-D", "FOREGROUND"]
#ENTRYPOINT ["httpd", "-D", "FOREGROUND"]