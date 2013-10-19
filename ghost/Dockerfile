
FROM ubuntu:latest
MAINTAINER Alexis Couronne
 
# update system
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y python-software-properties wget unzip

RUN add-apt-repository ppa:chris-lea/node.js

RUN apt-get update

RUN apt-get install -y nodejs

RUN mkdir /ghost

RUN cd /ghost && wget -O ghost.zip http://ghost.org/zip/ghost-0.3.3.zip

RUN cd /ghost && unzip ghost.zip

RUN rm /ghost/ghost.zip

RUN cd /ghost && npm install --production

ADD config.js /ghost/config.js

EXPOSE 2368

WORKDIR /ghost

CMD ["npm", "start", "--production"]
