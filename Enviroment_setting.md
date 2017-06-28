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
Then configure plugins by put this at the top of your .vimrc to use Vundle. Remove plugins you don't need, they are for illustration purposes. In this setting, I just set "nerdtree" plugin for me. Then launch `vim` and run `:PluginInstall`
```
    set nocompatible " be iMproved, required
    filetype off " required
    " set the runtime path to include Vundle and initialize
    set rtp+=~/.vim/bundle/Vundle.vim
    call vundle#begin()
    " alternatively, pass a path where Vundle should install plugins
    "call vundle#begin('~/some/path/here')

    " let Vundle manage Vundle, required
    Plugin 'VundleVim/Vundle.vim'
    Plugin 'scrooloose/nerdtree'
    " The following are examples of different formats supported.
    " Keep Plugin commands between vundle#begin/end.
    " plugin on GitHub repo
    Plugin 'tpope/vim-fugitive'
    " plugin from http://vim-scripts.org/vim/scripts.html
    " Plugin 'git://git.wincent.com/command-t.git'
    " git repos on your local machine (i.e. when working on your own plugin)
    " The sparkup vim script is in a subdirectory of this repo called vim.
    " Pass the path to set the runtimepath properly.

    Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
    " Install L9 and avoid a Naming conflict if you've already installed a
    " different version somewhere else.
    Plugin 'ascenator/L9', {'name': 'newL9'}

    " All of your Plugins must be added before the following line
    call vundle#end() " required
    filetype plugin indent on " required
    " To ignore plugin indent changes, instead use:
    "filetype plugin on
    "
    " Brief help
    " :PluginList - lists configured plugins
    " :PluginInstall - installs plugins; append `!` to update or just :PluginUpdate
    " :PluginSearch foo - searches for foo; append `!` to refresh local cache
    " :PluginClean - confirms removal of unused plugins; append `!` to auto-approve removal
    "
    " see :h vundle for more details or wiki for FAQ
    " Put your non-Plugin stuff after this line
    map <C-n> :NERDTreeToggle<CR>

    " encoding settings
    set fileencodings=utf-8,ucs-bom,gb18030,gbk,gb2312,cp936
    set termencoding=utf-8
    set encoding=utf-8
    set number
    set ts=4
```

## Python setting
1. Make sure you have `pip`, if not, install it.

2. Install `virtualenv` for your python:
```
    pip install virtualenv
```

3. Install `virtualenvwrapper` for your python and set it as the doc. But attention, if you change the shell to `zsh`, you need to modify `.zshrc` rather thant `.bashrc`.
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