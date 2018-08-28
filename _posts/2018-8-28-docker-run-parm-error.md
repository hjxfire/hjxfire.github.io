---
layout: post
title:  'docker run命令运行时的executable file not found in $PATH": unknown错误'
categories: docker
tags:  docker
author: hjxfire
---

* content
{:toc}
今天在使用docker run命令时出现了以下错误.
```
docker: Error response from daemon: OCI runtime create failed: container_linux.go:348: starting container process caused "exec: \"--name\": executable file not found in $PATH": unknown.
```
查阅资料发现是容器名称必须在所有参数之后.





## 问题命令
```
docker run hjxfire/struts2.5.16 --name struts2 -p 5000:8080
```
## 报错信息
```
docker: Error response from daemon: OCI runtime create failed: container_linux.go:348: starting container process caused "exec: \"--name=struts2.5.16\": executable file not found in $PATH": unknown.
```

## 正确命令
```
docker run  --name struts2 -p 5000:8080 hjxfire/struts2.5.16
```