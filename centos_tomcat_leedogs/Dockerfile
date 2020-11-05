FROM centos
MAINTAINER “Yourname" <lee.pierce@aa.com>
RUN yum -y update
RUN yum -y install net-tools
RUN yum -y install bind-utils
RUN yum -y install java-1.8.0-openjdk*
RUN yum -y install wget
WORKDIR /opt
RUN wget https://ftp.wayne.edu/apache/tomcat/tomcat-9/v9.0.39/bin/apache-tomcat-9.0.39.tar.gz
RUN gunzip *gz
RUN tar xvfp *tar
RUN rm *tar
COPY ./leeJS /opt/apache-tomcat-9.0.39/webapps/leeJS
WORKDIR /opt/apache-tomcat-9.0.39/bin 
ENTRYPOINT ["/opt/apache-tomcat-9.0.39/bin/catalina.sh","run"]
