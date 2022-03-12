## 安装
```
sudo apt-get install python3-pip 
sudo pip install --upgrade pip 

```

升级后可能会报错 `AttributeError: 'module' object has no attribute 'main' `   
可以把 `/usr/bin/pip` 修改改为：
```
from pip import __main__
if __name__ == '__main__':
    sys.exit(__main__._main())
```
