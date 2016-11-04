# LRKJ-CMS

LRKJ-CMS 是一个基于 docker 容器技术开发的一个 nodejs-cms 开发环境

## ability

* 帮助项目快速部署, 简便的预发布系统, 实现毫秒级的无缝切换
* 统一开发环境, 提高开发效率
* 提供可持续集成的 LRKJ-CI 系统

## quick start

快速开始

### 安装 docker

* window系统, 要求是win10并且是xx版本以上

```
1.首先去官网下载安装包
https://docs.docker.com/docker-for-windows/
2.安装完成后, 进入docker配置, 配置 'Shared Dirves', 添加开发目录
```

* mac系统

```
1.首先去官网下载安装包
https://docs.docker.com/docker-for-mac/
2.安装完成后, 进入docker配置, 配置 'File Sharing', 添加开发目录
```

### 拉取开发环境 image

```
docker login -u liangakcm@163.com -p zhugeliang558125 hub.c.163.com
docker pull hub.c.163.com/promeyang/node-cms:latest
```

### 拉取代码仓库 git

```
1.拿到分配项目的git地址
2.在本地检出开发目录
3.配置好开发目录与开发环境的文件系统映射
```

### 启动环境容器 container

```
docker run --name=nodecms -t -i -p [映射的端口]:80 -p 50000:50000 -p 27017:27017 -v [开发机上开发目录]:/data/LRKJ-CMS.com/LRKJ-CMS/ [镜像ID] /bin/bash

```

### 运行环境 env

```
cmsdev env -- 只需要在第一次启动容器的时候执行, 以后不需要
cmsdev node {app|wx|www|admin} -- 开发调试时执行的命令
```

## docker 常用命令

* docker info -- 查看docker信息
* docker images [-a] -- 查看镜像列表[全部]
* docker ps [-a] -- 查看容器列表[全部]
* docker exec -it [容器名字] /bin/bash -- 进入容器
* docker rm [容器ID] [-f] -- 删除容器[强制删除]
* docker restart [容器ID] -- 重启容器
* docker run --name=nodecms -t -i -p 80:80 -p 50000:50000 -v /data/:/data/ 1e8a237d4bb0 /bin/bash -- 启动容器
