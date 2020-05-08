---
title: 香橙派zero的Docker编译环境
date: 2020-05-08 10:45:28
tags:
---

```dockerfile
FROM ubuntu:bionic

MAINTAINER The OrangePi environment <xiaogsblog@gmail.com>

ADD sources.list /etc/apt/sources.list

RUN apt-get update \
	&& apt-get install -y vim \
	&& apt-get install -y unzip \
	&& apt-get install -y bsdtar \
	&& apt-get install -y mtools \
	&& apt-get install -y u-boot-tools \
	&& apt-get install -y pv \
	&& apt-get install -y bc \
    && apt-get install -y gcc \
	&& apt-get install -y automake \
	&& apt-get install -y make \
	&& apt-get install -y curl \
	&& apt-get install -y lib32z1 \
	&& apt-get install -y lib32z1-dev \
	&& apt-get install -y dosfstools \
	&& apt-get install -y figlet \
	&& apt-get install -y gcc-arm-linux-gnueabi \
	&& apt-get install -y g++-arm-linux-gnueabi \
	&& apt-get install -y device-tree-compiler \
	&& apt-get install -y debootstrap \
	&& apt-get install -y cpio
	
ENV ARCH arm
ENV CROSS_COMPILE arm-linux-gnueabi-

CMD ["arm-linux-gnueabi-gcc","-v"]
```

