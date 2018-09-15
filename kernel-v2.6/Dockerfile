FROM ubuntu:14.04
MAINTAINER Yi-Soo An <yisooan@gmail.com>

# RUN sed -i "s/archive.ubuntu.com/mirror.kakao.com/g" /etc/apt/sources.list

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y build-essential git wget curl libncurses5-dev

WORKDIR /root
RUN mkdir mpoint
