# Enviroment settings and commands
Here are some very useful configs and commands for me to build a work enviroment in linux (unbunt / centos) platform, some also may be suitable for macOS.

## Linux setting
1. Generating a new SSH key  
```
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"  
```

2. Set the SSH config file  
`~/.ssh/config`  
```
    Host [serverName]  
        HostName [IP]  
        Port [port number]  
        User [username]  
```

3. Set the authorized_keys to allow SSH without password (use the public key). For ubuntu, openssh server need to be installed first.  
Put your `id_rsa.pub` in server and run  
`cat id_dsa.pub >> ~/.ssh/authorized_keys`  
(Be worth mentioning, there is also a ssh tool for windows, you can find it in  
https://www.openssh.com/  
You can make the same setting such as config and authorized_keys.)  
If it fails, maybe you need to verified your permissions are correct, you can fix it like so:
```
    chmod 700 ~/.ssh 
    chmod 600 ~/.ssh/authorized_keys
```

4. Change the shell to `zsh` and install `oh-my-zsh`. But attention, if you change the shell to `zsh`, you need to modify `.zshrc` rather thant `.bashrc`.
```
    chsh -s /bin/zsh
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## Vim setting
1. User vundle to configure vim enviroment  
`git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`  
Then configure plugins by put this at the top of your .vimrc to use Vundle. Remove plugins you don't need, they are for illustration purposes. In my setting, I just set "nerdtree" plugin for me. Then launch `vim` and run `:PluginInstall`


## Python setting
1. Make sure you have `pip`, if not, install it.

2. Install `virtualenv` for your python:
```
    pip install virtualenv
```

3. Install `virtualenvwrapper` for your python and set it follow the [document](https://virtualenvwrapper.readthedocs.io/en/latest/). But attention, if you change the shell to `zsh`, you need to modify `.zshrc` rather thant `.bashrc`.
```
    pip install virtualenvwrapper
```
4. Make a python3 enviroment
```
    mkvirtualenv --python=python3 [nameOfEnvironment]
```


## Some useful commands

1. Use the source in China to speedup the pip install
```
    pip install [packageName] -i https://pypi.doubanio.com/simple
```

2. Checking the direcory and file size
```
    du -sh *
```

3. git  
![](git.png)  
Initial, add remote reponsitory, and push(firstly):
```
    git init
    git remote add <remote_name> <remote_repo_url>
    git push -u <remote_name> <local_branch_name>
```




## Reference
SSH key:  
```
    https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/  
```

SSH config:  
```
    http://zlong.org/2015/06/08/ssh-config/
```

authorized_keys:  
```
    http://www.linuxproblem.org/art_9.html  
    https://stackoverflow.com/questions/6377009/adding-public-key-to-ssh-authorized-keys-does-not-log-me-in-automatically  
```

zsh and oh-my-zsh:  
```
    https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH  
    https://github.com/robbyrussell/oh-my-zsh
```

Use vundle to configure vim enviroment:
```
    https://github.com/VundleVim/Vundle.vim
    https://github.com/scrooloose/nerdtree
```

virtualenv and virtualenvwrapper:
```
    https://virtualenv.pypa.io/en/stable/
    https://virtualenvwrapper.readthedocs.io/en/latest/
```

make python3 virtualenv:
```
    https://stackoverflow.com/questions/16123459/virtualenvwrapper-and-python-3
```

git:  
```
    https://www.atlassian.com/git/tutorials/setting-up-a-repository
```
