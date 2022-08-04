#### 在windows下安装

```bash
https://docs.microsoft.com/zh-cn/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package

https://www.docker.com/get-started/


C:\Users\zyy>docker --version
Docker version 20.10.17, build 100c701
```

#### docker在debian10下安装

```bash
# 移除旧版
apt-get remove docker docker-engine docker.io containerd runc

# 安装
curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun
```

#### docker在CentOS7上的安装

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
docker pull centos:centos7

# 查看镜像


# 删除镜像
```

##### 网络

- network=none ,docker 容器就不会分配局域网的IP主机网络  
- network=host，docker容器的网络会附属在主机上，两者是互通的

```bash
# 查看 docker 网络
C:\Users\zyy>docker network ls
NETWORK ID     NAME      DRIVER    SCOPE
fb5b980823a2   bridge    bridge    local
0c3a2854e441   host      host      local
d88a053e6775   none      null      local

# 查看 container 的IP
cat /etc/hosts
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}'
```