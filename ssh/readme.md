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

## SSH服务端配置
ssh-server配置文件位于/etc/ssh/sshd_config    
1、修改默认端口：默认Port为22,并且已经注释掉了；修改是把注释去掉，并修改成其它的端口。   
2、禁止root用户远程登陆：修改PermitRootLogin，默认为yes且注释掉了；修改是把注释去掉，并改成no。    
3、PermitEmptyPasswords   no不允许空密码用户login 

### SSH的公钥认证配置： 
修改 /etc/ssh/sshd_config 文件    
RSAAuthentication yes        # 启用 RSA 认证（默认是注释掉的，将注释去掉，如果不是yes，改为yes）     
PubkeyAuthentication yes     # 启用公钥认证（默认是注释掉的，将注释去掉，如果不是yes，改为yes）    
AuthorizedKeysFile   %h/.ssh/authorized_keys   # 公钥存放位置，可自定义

之后重新启动ssh服务:/etc/init.d/ssh restart 

## 配置免密登录（从A登录B）
客户端A使用命令生成公钥id_rsa.pub和私钥id_rsa，默认位于~/.ssh
```
ssh-keygen -t rsa -f id_rsa
```
把公钥拷贝到需要登录服务端主机B的~/.ssh/authorized_keys
```
ssh-copy-id user@server
```
或 
```
scp ~/.ssh/id_rsa.pub user@server:~/.ssh/authorized_keys
```
即可远程免密登录。    
注意服务端B主机文件权限
```
chmod 755 ~
chmod 755 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```
A主机ssh-agent、ssh-add
