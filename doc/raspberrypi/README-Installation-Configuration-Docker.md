# Installation / Configuration Docker

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Docker](#install-docker)





## Check Prerequisites

 * Raspbian required





## Install Docker

Execute the following command via console

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
```

Verify the new file : get-docker.sh

```bash
ls
```

Execute the following command via console -> The script will start the process of installing Docker

```bash
sh get-docker.sh
```

By default, only root users are able to access Docker

For other users to execute Docker commands, they must be members of the "docker" group, which was created by the installation script

Add your current user to the "docker" group by running the following command:

```bash
sudo usermod -aG docker $USER
```

Other Case

```bash
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "/home/$USER/.docker" -R
```



Optional : sudo reboot




## Verify Docker

Execute the following command via console

```bash
docker --version
```

Execute the following command via console

```bash
docker run hello-world
```