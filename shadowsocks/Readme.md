# 服务端  

## 安装
Debian / Ubuntu:
```
apt-get install python-pip
export LC_ALL=C
pip install shadowsocks
```

配置/etc/shadowsocks.json如下：(自定义端口及密码)
```
{
  "server":"0.0.0.0",
  "port_password": {
        "8888": "123456",
    },
    "timeout": 300,
    "method": "aes-256-cfb",
    "fast_open": false
}
```

运行ssserver
```
sudo ssserver -c /etc/shadowsocks.json -d start
```
