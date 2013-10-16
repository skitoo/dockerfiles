
FROM ubuntu:latest
MAINTAINER Alexis Couronne
 
# update system
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y
 
RUN apt-get install -y python-software-properties wget
 
RUN add-apt-repository ppa:webupd8team/java -y
RUN apt-get update
 
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install -y oracle-java7-installer
 
RUN wget -O /gitbucket.war https://github.com/takezoe/gitbucket/releases/download/1.6/gitbucket.war
 
EXPOSE 8080

VOLUME ["/root"]
 
CMD ["/usr/bin/java", "-jar", "/gitbucket.war"]
