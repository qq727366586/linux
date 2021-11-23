## docker 安装依赖

```kotlin
yum install -y yum-utils device-mapper-persistent-data lvm2
```

## 添加yum仓库

```csharp
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
yum makecache
```

## 安装docker-ce

```undefined
dnf -y  install docker-ce --nobest
```

## docker开机自启

```bash
systemctl enable --now docker
```

## 添加当前用户到docker group

配置镜像地址

```undefined
vi /etc/docker/daemon.json
```

```json
{
  "registry-mirrors": ["https://registry.docker-cn.com"]
}

service docker restart
```

```bash
usermod -aG docker $USER
newgrp docker
```

## 可以愉快到玩耍了！

注：命令在root下执行 or 加sudo

# docker-compose

Linux 上我们可以从 Github 上下载它的二进制包来使用，最新发行的版本地址：https://github.com/docker/compose/releases。

运行以下命令以下载 Docker Compose 的当前稳定版本：

```
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

要安装其他版本的 Compose，请替换 1.24.1。

将可执行权限应用于二进制文件：

```
$ sudo chmod +x /usr/local/bin/docker-compose
```

创建软链：

```
$ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

测试是否安装成功：

```
$ docker-compose --version
cker-compose version 1.24.1, build 4667896b
```

**注意**： 对于 alpine，需要以下依赖包： py-pip，python-dev，libffi-dev，openssl-dev，gcc，libc-dev，和 make。

