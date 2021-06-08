# Installation / Configuration Pyenv-Virtualenvs

pyenv-virtualenvs is a pyenv plugin for working with virtual environments

Used in conjunction with pyenv

https://github.com/pyenv/pyenv-virtualenv

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Pyenv-Virtualenvs](#install-pyenv-virtualenvs)
- [Create Virtual Environment](#create-virtual-environment)
- [Remove Virtual Environment](#remove-virtual-environment)
- [Activate Virtual Environment](#activate-virtual-environment)
- [Deactivate Virtual Environment](#deactivate-virtual-environment)
- [Verify Virtual Environment](#verify-virtual-environment)





## <a name="check-prerequisites">Check Prerequisites</a>

Require pyenv





## <a name="install-pyenv-virtualenvs">Install Pyenv-Virtualenvs</a>

Execute the following command via console

```bash
# Installation
$ git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv
 
$ git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv
 
# Brew
$ brew install pyenv-virtualenv
 
# Load initializer
 
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.zshrc
 
# Reset ~/.zshrc
$ source ~/.zshrc
```




## <a name="create-virtual-environment">Create Virtual Environment</a>

Execute the following command via console

```bash
# Create Virtual Environment for specific version with custom name
#   pyenv virtualenv <python_version> <environment_name>
 
# Create Virtual Environment for 3.9.4 version with name venvacme3.9.4
$ pyenv virtualenv 3.9.4 venvacme3.9.4
 
# Create Virtual Environment for active version with custom name
#   pyenv virtualenv <environment_name>
 
# Create Virtual Environment for active version with name venvacme3.9.4
$ pyenv virtualenv venvacme3.9.4
```




## <a name="remove-virtual-environment">Remove Virtual Environment</a>

Execute the following command via console

```bash
# Remove virtual environment
$ pyenv virtualenv 3.9.4 venvacme3.9.4
```




## <a name="activate-virtual-environment">Activate Virtual Environment</a>

Execute the following command via console

```bash
# Activate Virtual Environment
#   pyenv activate <environment_name>
 
# Activate custom virtual environment
$ pyenv activate venvacme3.9.4
 
# Activar un entorno virutal de forma local
$ pyenv local myproject
```

The active environment will be displayed at the prompt
A Python version file can be created which indicates the current active version.





## <a name="deactivate-virtual-environment">Deactivate Virtual Environment</a>

Execute the following command via console

```bash
# Deactivate virtual environment
$ pyenv deactivate
```




## <a name="verify-virtual-environment">Verify Virtual Environment</a>

Execute the following command via console

```bash
# Verify python pip version 
$ pyenv which python
 
# Verify active pip version 
$ pyenv which pip
```
