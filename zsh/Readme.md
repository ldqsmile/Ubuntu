### zsh安装
正式安装zsh、git和wget，获取并自动按照oh-my-zsh：
```
sudo apt-get install zsh git wget
wget --no-check-certificate https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```
替换bash为zsh：
```
chsh -s /bin/zsh
```
最后重启：
```
sudo reboot
```
### 配置on-my-zsh插件、主题
官方有丰富的插件，可见：    
https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview   
和多种主题：    
https://github.com/robbyrussell/oh-my-zsh/wiki/themes       
修改~/.zshrc即可配置    
```
ZSH_THEME="ys"    #主题
plugins=(git extract z)    #插件
```   
也可以下载第三方插件，如zsh-autosuggestions，方法如下：   
```
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions 
```
再修改~/.zshrc：   
```
plugins=(zsh-autosuggestions)   
```
配置补全的字体颜色为ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE，如fg=10.   
可直接在zsh-autosuggestions.zsh中修改:    
```
vim  $ZSH_CUSTOM/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
``` 
或者修改$ZSH_CUSTOM/plugins/zsh-autosuggestions/src/config.zsh后移动到$ZSH_CUSTOM下:   
```
vim config.zsh
mv config.zsh $ZSH_CUSTOM
```

如incr.zsh插件:    
```
mkdir $ZSH_CUSTOM/plugins/incr    
wget http://mimosa-pudica.net/src/incr-0.2.zsh -O $ZSH_CUSTOM/plugins/incr/incr.zsh
```
在~/.zshrc添加一句：
```
source $ZSH_CUSTOM/plugins/incr/incr*.zsh
```

如autojump插件，需要先安装autojump
```
sudo apt-get install autojump
```
再修改~/.zshrc：
```
plugins=(autojump)   
. /usr/share/autojump/autojump.sh
```

修改完以后，source ~/.zshrc生效。
