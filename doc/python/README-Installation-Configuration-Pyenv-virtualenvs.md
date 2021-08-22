# Installation / Configuration Pyenv-Virtualenvs

pyenv-virtualenvs is a pyenv plugin for working with virtual environments for across varying versions of Python

* Use on Linux-like systems
* Manage virtualenv and conda enviroments
* Used in conjunction with pyenv -> multiple Python version and multiple virtual environments
* Ensure that all libraries and dependancies that are installed in that folder are completely isolated

https://github.com/pyenv/pyenv-virtualenv

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Pyenv-Virtualenvs](#install-pyenv-virtualenvs)
- [Create Virtual Environment](#create-virtual-environment)
- [Remove Virtual Environment](#remove-virtual-environment)
- [Activate Virtual Environment](#activate-virtual-environment)
- [Deactivate Virtual Environment](#deactivate-virtual-environment)
- [Verify Virtual Environment](#verify-virtual-environment)





## Check Prerequisites

Require pyenv





## Install Pyenv-Virtualenvs

Execute the following command via console

```bash
# Installation Option 1
$ git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv

# Installation Option 2
$ git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv
 
# Intallation Brew Option
$ brew install pyenv-virtualenv
```

Execute initializer

```bash
# Load initializer depends shell
#   * Bash shell
$ echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
#   * Z shell
$ echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.zshrc
 
# Reset ~/.zshrc
$ source ~/.zshrc
```

Execute Reset Shell

```bash
$ exec "$SHELL"
```





## Create Virtual Environment

Execute the following command via console

```bash
# Create Virtual Environment for specific version with custom name
#   pyenv virtualenv <python_version> <environment_name>
 
# Create Virtual Environment for 3.9.4 version with name venvacme3.9.4
pyenv virtualenv 3.9.4 venvacme3.9.4
 
# Create Virtual Environment for active version with custom name
#   pyenv virtualenv <environment_name>
 
# Create Virtual Environment for active version with name venvacme3.9.4
pyenv virtualenv venvacme3.9.4
```

Verify that a folder exists $(pyenv root)/versions with the <environment_name>




## Show Virtual Environments

Execute the following command via console

```bash
# Remove virtual environment
$ pyenv virtualenvs
```




## Remove Virtual Environment

Execute the following command via console

```bash
# Activate Virtual Environment
#   pyenv uninstall <environment_name>

# Option 1 : Remove virtual environment 
$ pyenv uninstall venvacme3.9.4

# Option 2 : Remove virtual environment 
$ pyenv virtualenv-delete venvacme3.9.4
```

Removing the directories in $(pyenv root)/versions and $(pyenv root)/versions/{version}/envs will delete the virtualenv





## Activate Virtual Environment

Execute the following command via console

```bash
# Activate Virtual Environment
#   pyenv activate <environment_name>
 
# Activate custom virtual environment
$ pyenv activate venvacme3.9.4
 
# Activate local custom virtual environment
$ pyenv local venvacme3.9.4
```

The active environment will be displayed at the prompt
A Python version file can be created which indicates the current active version.





## Deactivate Virtual Environment

Execute the following command via console

```bash
# Deactivate virtual environment
$ pyenv deactivate
```


