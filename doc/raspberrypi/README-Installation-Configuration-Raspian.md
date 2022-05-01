# Installation / Configuration Raspbian OS

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Raspbian](#install-raspbian)





## Check Prerequisites

 * Raspbian required

https://medium.com/geekculture/getting-started-with-raspberry-pi-and-installing-raspberry-pi-os-f20cbee4c008 





## Install Raspbian

Execute the following command via console

```bash
xxx
```





### Update your system

Execute the following command via console

```bash
sudo apt update && sudo apt upgrade
```





### Enable sudo without password

This provides the feature of not being requested the password every time you need to use sudo


Execute the following command via console

```bash
sudo visudo
```

This will open the nano editor with that configuration. Then add the following line at the end (we assume that the username is pi):

```bash
pi ALL=(ALL) NOPASSWD: ALL
```

Press CTRL+X, then enter to save the changes





### Install net-tools

Utility for managing network communications from the command line

Execute the following command via console

```bash
sudo apt install net-tools
```





### Install git

Utility for managing code and synchronize it with remote repositories

Execute the following command via console

```bash
sudo apt install git
```

git config --global user.name "Your Name"
git config --global user.email "youremail@yourdomain.com"

git config --list





### Install openssh-server

Utility for remotely connect to the Raspberry Pi

Execute the following command via console

```bash
sudo apt install openssh-server
```

After the installation, the SSH service will start automatically

Execute the following command via console

```bash
sudo systemctl status ssh
```




ONLY for developer
sudo apt install make libssl-dev libghc-zlib-dev libcurl4-gnutls-dev libexpat1-dev gettext





### Connect SSH 

Execute the following command via console

```bash
hostname
```

Execute the following command via console

```bash
ifconfig
```

Execute the following command via console

```bash
ssh <USER>@<HOSTNAME>.local

ssh <USER>@<IP_ADDRESS>
```




## Run all scripts from any directory

1. Locate the file : ~/.bashrc o ~/.zshrc  

2. Add the following to the file


```bash
export PATH="$HOME/.local/bin:$PATH"
```
