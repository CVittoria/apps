FROM ubuntu:bionic
MAINTAINER "Chris Vittoria (ch.vittoria@gmail.com)"

#Based on linuxserver ubuntu container
#Slim ubuntu with s6 overlay

ARG OVERLAY_VERSION="v1.22.0.0"
ARG OVERLAY_ARCH="amd64"

RUN  echo "**** add s6 overlay ****" && \
 curl -o \
 /tmp/s6-overlay.tar.gz -L \
	"https://github.com/just-containers/s6-overlay/releases/download/${OVERLAY_VERSION}/s6-overlay-${OVERLAY_ARCH}.tar.gz" && \
 tar xfz \
	/tmp/s6-overlay.tar.gz -C / 

