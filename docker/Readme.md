# 安装
先安装pip

## 安装最新版docker
```
curl -s https://get.docker.com/ | sh
```

## 启动docker服务
```
sudo service docker start
```

## 安装compose
```
pip install docker-compose 
```

在使用 docker 命令时，如果不想使用 sudo，请创建名为 docker 的 用户组并向其中添加用户，重启电脑生效。
```
sudo groupadd docker
sudo usermod -aG docker $USER
```
