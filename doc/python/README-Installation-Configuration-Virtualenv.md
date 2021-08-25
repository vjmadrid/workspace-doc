# Installation / Configuration Virtualenv

[virtualenv](https://pypi.org/project/virtualenv/) is command-line tool used the default tool that works by creating isolated directories within a Python application’s base directory and installs packages within that environment

Alternative : venv

> Note that with the release of Python 3.8, Virtualenv has been deprecated
>
> Virtualenv is recommended for Python up to version 3.3. Newer versions of Python should use venv instead

* Create isolated virtual environments -> own set of dependencies
    * Creating an environment with its own installation directory and corresponding libraries
* Each project is isolated within its own virtual environment, with its own version of Python, the probability of dependency conflicts is minimized 
* Has been part of the Python core Python 2
* manages virtual environments for a specific Python version
* These packages, once installed, do not interfere with other packages outside of the virtual environment directory

a more full-featured version of venv that ships as a third party package rather than in
the Python core, but you’ll need pip to manage the packages in your virtual environment.
pyenv - adds the capability to manage installed versions of Python, alongside pyenv-virtualenv to
create the actual virtual environments. Still need pip though


Installing And Managing Python Dependencies With Pipenv
Pipenv takes dependency management a step further than virtualenv. While the functionality is very similar to virtualenv, a few key features have been added to help limit some of the disadvantages of using virtualenv. The installation instructions can be found here.

https://pipenv.kennethreitz.org/en/latest/install/#installing-pipenv



Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Virtualenv](#install-virtualenv)
- [Verify Virtualenv](#verify-Virtualenv)
- [Create Virtual Environment](#create-virtual-environment)
- [Activate Virtual Environment](#activate-virtual-environment)
- [Deactivate Virtual Environment](#deactivate-virtual-environment)





## Check Prerequisites

It is available together with the Python installation

 * Since Python 3 version 3.6





## Install Virtualenv

Execute the following command via console

```bash
pip3 install virtualenv
```

This command creates a new subdirectory within the current directory named my-virtual-environment




## Verify Virtualenv

Execute the following command via console

```bash

```





## Create Virtual Environment

Select path
 * cd into the project directory where you want the virtual environment

Execute the following command via console

```bash
virtualenv <my-virtual-environment-name>
```





## Activate Virtual Environment

Localize path :

```bash
cd <my-virtual-environment-name>/
```

Execute the following command via console

```bash
source bin/activate
```

Verify prompt





## Deactivate Virtual Environment

Localize path :

```bash
cd <my-virtual-environment-name>/
```

Execute the following command via console

```bash
source bin/deactivate
```

Verify prompt




