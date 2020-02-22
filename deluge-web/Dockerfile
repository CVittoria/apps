FROM lsiobase/ubuntu:bionic
MAINTAINER "Chris Vittoria ch.vittoria@gmail.com"

#Based on linuxserver deluge container
#Split deluge-web to separate container

RUN \
 echo "**** add repositories ****" && \
 apt-get update && \
 apt-get install -y \
	gnupg && \
 apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys C5E6A5ED249AD24C && \
 echo "deb http://ppa.launchpad.net/deluge-team/stable/ubuntu bionic main" >> \
	/etc/apt/sources.list.d/deluge.list && \
 echo "deb-src http://ppa.launchpad.net/deluge-team/stable/ubuntu bionic main" >> \
	/etc/apt/sources.list.d/deluge.list && \
 echo "**** install packages ****" && \
 apt-get update && \
 apt-get install -y deluge-web \
 	jq && \
 echo "**** cleanup ****" && \
 rm -rf \
	/tmp/* \
	/var/lib/apt/lists/* \
	/var/tmp/* 


# add local files
COPY root/ /

# ports and volumes
EXPOSE 8112
VOLUME /config 
