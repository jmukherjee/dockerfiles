#
# Apache Dockerfile
#
# https://github.com/jmukherjee/dockerfiles/apache
#

# Pull base image.
FROM jmukherjee/ubuntu

# Install Apache.
RUN DEBIAN_FRONTEND=noninteractive apt-get -y install apache2
RUN DEBIAN_FRONTEND=noninteractive update-rc.d apache2 defaults
RUN DEBIAN_FRONTEND=noninteractive lynx-cur sysstat acl

RUN a2enmod rewrite

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid

RUN chgrp -R www-data /var/www/html
RUN chmod -R 775 /var/www/html

# Define working directory.
WORKDIR /var/www/html

# Define default command.
CMD ["bash"]

EXPOSE 80
EXPOSE 443