![](E:\myOftenUse\myworkSpace\blogDemo\docker-notes\docker.jpg)

### 概述

> docker 是一款用来开发、部署、运行应用的虚拟化平台，跟虚拟机相比它不会虚拟一个完整的操作系统，而是直接运行在我们的宿主机上，容器没有自己的内核所以轻便很多。而且每个容器之间是相互隔离的有自己的文件系统，所以我们可以像使用集装箱一样去组合自己的应用。

### 优点

1. 比较轻便、可以秒级启动服务，节省开发与部署时间；
2. 方便运维，保证开发、测试、线上环境高度一致；
3. 高效利用计算机资源，可以在服务器上虚拟很多我们需要的各个版本的容器；
4. 交付更加方便，以前我们需要交付各种源码、程序包、部署文档，现在只需要交付一个`docker image`；

### 安装

#### `docker`的基本组成

> 镜像

类似于一个模板，可以使用镜像启动多个服务

> 容器

利用镜像启动的一个或一组服务叫做容器

> 仓库

存放镜像的远程仓库`dockerhub`，类似于`github` ，地址：[官网地址](https://hub.docker.com/)

#### 宿主环境

```shell
# 内核
# uname -r
5.4.0-48-generic

# 系统版本
# cat /etc/os-release 
NAME="Ubuntu"
VERSION="18.04.5 LTS (Bionic Beaver)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 18.04.5 LTS"
VERSION_ID="18.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=bionic
UBUNTU_CODENAME=bionic
```

#### 安装命令

```shell
# 如有历史版本，先卸载
sudo apt-get remove docker docker-engine docker.io containerd runc
# 更新apt索引
sudo apt-get update
# 安装依赖包
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
# 添加 Docker 的官方 GPG 密钥：
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
# 验证指纹
sudo apt-key fingerprint 0EBFCD88
# 给docker设置仓库地址<中国科技大学镜像仓库>
sudo add-apt-repository \
   "deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/ \
  $(lsb_release -cs) \
  stable"
# 更新apt索引
sudo apt-get update
# 安装社区版的docker
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

#### 查看docker版本信息

```shell
# docker version
Client: Docker Engine - Community
 Version:           19.03.13
 API version:       1.40
 Go version:        go1.13.15
 Git commit:        4484c46d9d
 Built:             Wed Sep 16 17:02:36 2020
 OS/Arch:           linux/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          19.03.13
  API version:      1.40 (minimum version 1.12)
  Go version:       go1.13.15
  Git commit:       4484c46d9d
  Built:            Wed Sep 16 17:01:06 2020
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.3.7
  GitCommit:        8fba4e9a7d01810a393d5d25a3621dc101981175
 runc:
  Version:          1.0.0-rc10
  GitCommit:        dc9208a3303feef5b3839f4323d9beb36df0a9dd
 docker-init:
  Version:          0.18.0
  GitCommit:        fec3683
```

### 常用命令

#### 帮助命令

#### 镜像命令

#### 容器命令



### 镜像

### 容器卷

### `Dockerfile`

### Docker 网络

### 实战

