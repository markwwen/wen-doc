# Enviroment setting
Here are some very useful configs and commands for me to build a work enviroment in linux (unbunt / centos) platform.

## Linux setting
1. Generating a new SSH key  
Command:  
```
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"  
```

2. Set the SSH config file  
`~/.ssh/config`  
```
    Host server1  
        HostName [IP]  
        Port [port number]  
        User [username]  
```

3. Set the authorized_keys to allow SSH without password (use the id_rsa.pub)



## Reference
SSH key:  
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/  

SSH config:  
http://zlong.org/2015/06/08/ssh-config/