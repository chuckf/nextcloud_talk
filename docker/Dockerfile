FROM scratch
MAINTAINER https://github.com/CentOS/sig-cloud-instance-images
ADD centos-7-docker.tar.xz /
ADD nextcloud-11.0.2.zip /root
ADD remi-release-7.rpm /root

LABEL name="CentOS Base Image" \
    vendor="CentOS" \
    license="GPLv2" \
    build-date="20161214"

RUN yum update -y
RUN yum install wget epel-release -y
RUN wget http://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN wget https://download.nextcloud.com/server/releases/nextcloud-11.0.2.zip
RUN yum install ./remi-release-7.rpm -y
RUN yum-config-manager --enable remi-php70 -y
RUN yum install vim httpd mariadb-server php -y

CMD ["/bin/bash"]
