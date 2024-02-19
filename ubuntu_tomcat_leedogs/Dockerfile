FROM ubuntu
MAINTAINER “Yourname" <lee.pierce@aa.com>
RUN apt-get update
RUN apt-get -y install openjdk-17-jre
RUN apt-get -y install wget
WORKDIR /opt
RUN wget --no-check-certificate https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.18/bin/apache-tomcat-10.1.18.tar.gz
RUN gunzip *gz
RUN tar xvfp *tar
RUN rm *tar
COPY ./leeJS /opt/apache-tomcat-10.1.18/webapps/leeJS
WORKDIR /opt/apache-tomcat-10.1.18/bin
ENTRYPOINT ["/opt/apache-tomcat-10.1.18/bin/catalina.sh","run"]

