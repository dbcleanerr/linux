### 在windows下使用docker

#### 安装WSL2
> https://docs.microsoft.com/zh-cn/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package

#### 安装 docker desktop
> https://www.docker.com/get-started/

```bash
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

```bash
# 查看版本
docker --version
```