# Installation / Configuration Ansible With Pip

Pip (pip installs packages) is the package management standard for Python

[pip](https://pip.pypa.io/en/stable/)
[pip client](https://pip.pypa.io/en/stable/)

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Ansible With Pip](#install-ansible-with-pip)






## <a name="check-prerequisites">Check Prerequisites</a>

 * Verify that pyenv is installed by running : pyenv --version
 * Verify pyenv version >= 1.2.27
 * Verify that you have installed python version 3.9.4 from pyenv : pyenv version
    * If it does NOT exist, you need to install it : pyenv install -v 3.9.4
    * If it is NOT active, you need to activate it : pyenv global 3.9.4
 *Verify that a virtual working environment for python version 3.9.4 has been created from pyenv-virtualenv.
    * If it does NOT exist : pyenv virtualenv venvcistec3.9.4
    * If NOT active, you need to activate it : pyenv activate venvcistec3.9.4
        * source /Users/XXXX/.pyenv/versions/3.9.4/envs/venvcistec3.9.4/bin/activate
 * Check the activated version : pyenv version
    * It should be the one set for the version of Python and the virtual environment above.
 * Check the active python version : pyenv which python
 * Upgrade pip : python -m pip install --upgrade pip





## <a name="install-ansible-with-pip">Install Ansible With Pip</a>

 * Installation with pip on the isolated environment :
    * python -m pip install --user ansible==2.10.9
 * Verify the installation : ansible --version
 * Check the execution aspects :
    * config file
    * configured module search path
    * ansible python module location

