FROM ubuntu
MAINTAINER “Yourname" <lee.pierce@aa.com>
ARG DEBIAN_FRONTEND=noninteractive
RUN apt -y update
RUN apth -y install vim
RUN apt -y install dnsutils
RUN apt -y install openjdk-8-jdk-headless
RUN apt -y install tcptraceroute
RUN apt -y install curl
RUN apt -y install telnet
COPY ./minifi /opt/minifi
WORKDIR /opt/minifi
ENTRYPOINT ["/opt/minifi/bin/nonstop-minifi.sh","start"]
