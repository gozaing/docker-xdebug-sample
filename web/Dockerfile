FROM centos:6

RUN rpm -ivh http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm
RUN rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN yum install -y httpd
RUN yum install -y vim
RUN yum install --enablerepo=epel,remi-php55,remi -y \
                              php \
                              php-cli \
                              php-gd \
                              php-mbstring \
                              php-mcrypt \
                              php-mysqlnd \
                              php-pdo \
                              php-xml \
                              php-xdebug \
                              php-memcached

COPY httpd.conf /etc/httpd/conf.d/docker-sample.conf
COPY php.ini /etc/php.ini

EXPOSE 80
CMD ["/usr/sbin/apachectl", "-D", "FOREGROUND"]
