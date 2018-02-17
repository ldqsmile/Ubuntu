## 客户端
Ubuntu缺省已经安装了ssh client。
也可以使用命令进行安装
```
sudo apt-get install ssh
```
或者
```
sudo apt-get install openssh-client
```

## 服务端
Ubuntu缺省没有安装SSH Server，使用以下命令安装：
```
sudo apt-get install openssh-server
```
可以通过以下命令检查是否安装运行成功
```
ps -e|grep ssh
netstat -tlp
```
可以通过命令进行启动(start/stop/restart)
```
sudo /etc/init.d/ssh start
```

## SSH配置
ssh-server配置文件位于/etc/ssh/sshd_config
