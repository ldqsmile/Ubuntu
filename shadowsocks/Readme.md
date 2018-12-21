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

如果出现 `undefined symbol: EVP_CIPHER_CTX_cleanup` 报错，是由于在 openssl1.1.0 版本中，废弃了 `EVP_CIPHER_CTX_cleanup` 函数。把`/usr/lib/python2.7/site-packages/shadowsocks/crypto/openssl.py` 文件中，相应的 `EVP_CIPHER_CTX_cleanup` 改为 `EVP_CIPHER_CTX_reset` 即可（shadowsocks2.8.2为52行、111行）。

或者使用 shadowsocks 新版本 release 2.9.1 
