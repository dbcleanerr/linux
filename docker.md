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

```bash
# 查看版本
docker --version
```