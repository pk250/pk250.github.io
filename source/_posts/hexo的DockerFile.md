---
title: hexo的DockerFile
date: 2020-05-08 10:42:31
tags:
---

```dockerfile
FROM ubuntu:bionic

MAINTAINER The hexo environment <xiaogsblog@gmail.com>

ADD sources.list /etc/apt/sources.list

RUN apt-get update \
	&& apt-get install -y git \
	&& apt-get install -y npm \
	&& npm install hexo -g \
	&& npm install hexo-deployer-git --save

EXPOSE 4000

CMD ["hexo","version"]
```

