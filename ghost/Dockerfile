
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

RUN cd /ghost && wget -O ghost.zip https://github.com/TryGhost/Ghost/releases/download/0.3.2/Ghost-0.3.2.zip

RUN cd /ghost && unzip ghost.zip

RUN rm /ghost/ghost.zip

RUN cd /ghost && npm install --production

ADD config.js /ghost/config.js

EXPOSE 2368

WORKDIR /ghost

CMD ["npm", "start", "--production"]
