---
title: 荔枝派none的Docker编译环境
date: 2020-05-08 10:50:09
tags:
---

```dockerfile
FROM ubuntu:bionic

MAINTAINER The LiCheePi environment <xiaogsblog@gmail.com>

ADD sources.list /etc/apt/sources.list

RUN apt-get upgrade \
	&& apt-get update \
	&& apt-get install -y apt-utils \
	&& apt-get install -y lib32z1 \
	&& apt-get install -y lib32ncurses5 \
	&& apt-get install -y vim \
	&& apt-get install -y make \
	&& apt-get install -y gcc \
	&& apt-get install -y ncurses-dev \
	&& apt-get install -y bison \
	&& apt-get install -y flex \
	&& apt-get install -y bc \
	&& apt-get install -y swig \
	&& apt-get install -y libssl-dev \
	&& apt-get install -y unzip \
	&& apt-get install -y g++ \
	&& apt-get install -y patch \
	&& apt-get install -y wget \
	&& apt-get install -y cpio \
	&& apt-get install -y rsync \
	&& apt-get install -y git \
	&& apt-get install -y python \
	&& apt-get install -y python-dev
	
ENV ARCH arm
ENV CROSS_COMPILE arm-linux-gnueabi-

CMD ["arm-linux-gnueabi-gcc","-v"]
```

