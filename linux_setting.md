# Linux setting
Here are some very useful config and command for me to build a work enviroment in linux (unbunt / centos) platform.

1. Generating a new SSH key  
Command:  
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"  

2. Set the SSH config file  
~/.ssh/config  
    Host server1  
        HostName [IP]
        Port [port number]
        User [username]
