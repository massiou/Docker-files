FROM 32bit/ubuntu:14.04

MAINTAINER Matthieu Velay mvelay@gmail.com

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3E5C1192
RUN apt-get update
RUN apt-get -y install wget
RUN apt-get -y install openjdk-7-jre


RUN wget https://download.elastic.co/elasticsearch/elasticsearch/elasticsearch-2.2.0.deb
RUN dpkg -i elasticsearch-2.2.0.deb
RUN update-rc.d elasticsearch defaults

RUN echo "deb http://packages.elastic.co/kibana/4.4/debian stable main" | sudo tee -a /etc/apt/sources.list.d/kibana-4.4.x.list
RUN apt-get update
RUN apt-get -y --force-yes install kibana


RUN service elasticsearch start
RUN service kibana start
