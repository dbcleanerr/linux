### 在windows下安装

```bash
https://docs.microsoft.com/zh-cn/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package

https://www.docker.com/get-started/


C:\Users\zyy>docker --version
Docker version 20.10.17, build 100c701
```

### docker在CentOS7上的安装

```bash
yum install -y yum-utils device-mapper-persistent-data lvm2

yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

yum install -y docker-ce

systemctl start docker
```


### 基本命令

##### docker

```bash
# 查看版本
docker --version

# info
docker info
```

##### 容器

```bash
# 查看容器
docker container ls -a

# 启动容器
docker container start 73ec05a75472

# 停止容器
docker container stop 73ec05a75472

# 删除容器
docker container rm 73ec05a75472

# 运行容器
# -d: 后台运行
# --name: 指定名字
# --端口
docker run -d --name postgres14 -p 3721:3721 -e POSTGRES_PASSWORD=welcome postgres:14.4
```

##### 镜像

> https://hub.docker.com/

```bash
# 下载镜像

docker pull postgres:14.4
C:\Users\zyy>docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
postgres     14.4      1133a9cdc367   2 weeks ago   376MB



```