# Github way (recommended)
Install:  
```
curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash
```
 
Update: 
```
pyenv update  
```

Add the following to ~/.zshrc or ~/.bashrc
```
export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```
Then install python etc. (need some build-essential)
```
pyenv install 2.7.10
```
