FROM centos:7
MAINTAINER “Yourname" <lee.pierce@aa.com>
#RUN yum -y update
#RUN yum -y install net-tools
#RUN yum -y install bind-utils
RUN yum -y install java-1.8.0-openjdk*
RUN yum -y install wget
WORKDIR /opt
RUN wget --no-check-certificate https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.18/bin/apache-tomcat-10.0.18.tar.gz
RUN gunzip *gz
RUN tar xvfp *tar
RUN rm *tar
COPY ./leeJS /opt/apache-tomcat-10.0.18/webapps/leeJS
WORKDIR /opt/apache-tomcat-10.0.18/bin
ENTRYPOINT ["/opt/apache-tomcat-10.0.18/bin/catalina.sh","run"]

