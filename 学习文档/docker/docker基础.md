# docker基础

## 1.docker介绍

Docker 容器是资源分割和调度的基本单位，封装整个服务的运行时环境，用于构建、发布和运行发布式应用的一个框架。它是一个跨平台，可移植并且简单易用的容器解决方案。

## 2.docker优势

* 更高效的利用系统资源
* 更快速的启动时间
* 一致的运行环境
* 持续交付和部署
* 更轻松的迁移
* 更轻松的维护和扩展

## 3.docker应用场景

* 简化配置
* 代码流水线（Code Pipeline）管理
* 提高开发效率
* 隔离应用
* 整合服务器
* 调适能力
* 多租户环境
* 快速部署

## 4.docker核心概念

### 4.1 镜像

Docker 镜像类似于虚拟机镜像，可以将它理解为一个只读的模板。例如，一个镜像可以包含一个基本的操作系统环境，里面仅安装了 Apache 应用程序（或用户需要的其他软件）。可以把它称为一个 Apache镜像。
　　镜像是创建Docker 容器的基础。通过版本管理和增量的文件系统，Docker提供了一套十分简单的机制来创建和更新现有的镜像，用户甚至可以从网上下载一个已经做好的应用镜像，并直接使用。

### 4.2 容器

Docker 容器类似于一个轻量级的沙箱，Docker 利用容器来运行和隔离应用。容器是从镜像创建的应用运行实例。可以将其启动、开始、停止、删除，而这些容器都是彼此相互隔离的、互不相见的。
　　可以把容器看做是一个简易版的Linux系统环境（包括root用户权限、进程空间、用户空间和网络空间等）以及运行在其中的应用程序打包而成的盒子

### 4.3 仓库

Docker 仓库类似于代码仓库，它是Docker集中存放镜像文件的场所。
　　仓库注册服务器是存放仓库的地方，其上往往存放着多个地方。每个仓库集中存放某一类镜像，往往包括多个镜像文件，通过不同的标签（tag）来进行区分。一个仓库会包含同一个软件不同版本的镜像，而标签就常用于对应改软件的各个版本。我们可以通过 <仓库名>:<标签>的格式来指定具体是这个软件哪个版本的镜像。如果不给出标签，将以 latest 作为默认标签。以Nginx镜像为例，nginx 是仓库的名字，其内包含有不同的版本标签，如，1.12.2，我们可以通过 nginx:1.12.2来指定需要哪个版本的镜像。如果忽略了标签，比如nginx ，那将视为 nginx:latest。
　　Docker 仓库可以分为公开仓库（Public）和私有仓库（Private）两种形式。目前最大的公开仓库是Docker Hub， 存放了数量庞大的镜像供用户下载。国内还有（时速云、阿里云）等公开仓库。
 　  当用户不希望公开自己的镜像文件，Docker 也支持用户在本地网络内创建一个只能自己访问的私有仓库。当用户创建了自己的镜像之后就可以使用push命令将其上传到指定的公有或者私有仓库。这样下次在另外一台机器上使用该镜像时，只需要将其从仓库上pull 下来就可以了。

## 4.docker命令

### 4.1 docker基础命令

* 帮助命令

```bash
    docker --help
```

* docker版本信息

```bash
    docker -v
```

* docker详细信息

```bash
    docker version
```

* 登陆docker hub

```bash
    docker login
```

### 4.1 docker镜像管理

* 搜索镜像

```bash
    docker search
```

* 获取镜像

```bash
    docker pull
```

* 查看镜像

```bash
    docker images
```

* 获取镜像的元数据

```bash
    docker inspect
```

* 删除镜像

```bash
    docker rmi
```

* 将容器打包成镜像

```bash
    Docker commit
```

* dockerfile生成镜像

```bash
    docker build
```

* 导出镜像

```bash
    docker save centos > /tmp/docker_centos.tar
```

* 导入镜像

```bash
    docker load < /tmp/docker_centos.tar
```

* 镜像打标签

```bash
    docker tag centos centos:7.2
```

* 推送镜像到docker hub

```bash
    docker push xujunjie/centos
```

### 4.2 docker容器管理

* 创建容器

```bash
docker create
```

* 创建容器并启动

```bash
docker run
```

* 查看容器

```bash
docker ps
```

* 启动容器

```bash
docker start
```

* 重启容器

```bash
docker restart
```

* 停止容器

```bash
docker stop
```

* 杀掉一个运行容器

```bash
docker kill
```

* 删除容器

```bash
docker rm
```

* 进入容器

```bash
docker attach 容器编号
ssh root@ip
```

* 创建为终端

```bash
docker exec
```

* 查看容器运行的进程

```bash
docker top
```

* 查看容器的端口映射

```bash
docker port
```

* 查看容器的日志

```bash
docker logs
```

* 容器和主机间的文件拷贝

```bash
docker cp
```

* 查看容器的底层信息

```bash
docker inspect
```

## 2 参考

* [文档](https://www.cnblogs.com/yanjieli/p/10218842.html)

