# Installation / Configuration Virtualenv

[Virtualenv](https://pypi.org/project/virtualenv/) or venv is the default tool that works by creating isolated directories within a Python application’s base directory and installs packages within that environment

* manages virtual environments for a specific Python version
* These packages, once installed, do not interfere with other packages outside of the virtual environment directory



Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Virtualenv](#install-virtualenv)
- [Verify Virtualenv](#verify-Virtualenv)
- [Create directory for Virtualenv](#verify-pip-version)
- [Create directory for Virtualenv](#verify-pip-version)





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





## Create directory for Virtualenv

Select path

Execute the following command via console

```bash
virtualenv <my-virtual-environment-name>
```





## Activate Virtualenv

Localize path :

```bash
cd <my-virtual-environment-name>/
```

Execute the following command via console

```bash
source bin/activate
```

Verify prompt





## Deactivate Virtualenv

Localize path :

```bash
cd <my-virtual-environment-name>/
```

Execute the following command via console

```bash
source bin/deactivate
```

Verify prompt




