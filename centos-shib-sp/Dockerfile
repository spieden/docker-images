FROM centos:centos7

MAINTAINER Daniel Carleton <spieden@exaptic.com>

RUN yum -y update \
    && yum -y install wget \
    && wget http://download.opensuse.org/repositories/security://shibboleth/CentOS_7/security:shibboleth.repo -P /etc/yum.repos.d \
    && yum -y install httpd shibboleth.x86_64 mod_ssl python-setuptools\
    && yum -y clean all\
    && easy_install supervisor

COPY supervisord.conf /etc/

EXPOSE 80 443

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]

