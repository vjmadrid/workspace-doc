# Installation / Configuration Pip

Pip (pip installs packages) is the package management standard for Python

* Default installation method for installing Python packages
* Pip can installs packages globally or it can install them for specific users
* Pip relies on a strong community-maintained package repository to install third party packages that are not included with your standard Python 3 installation
* Python modules available on the [Python Module Index](https://docs.python.org/3/py-modindex.html)
* Provides diferent functions : install, uninstall and manage packages

[pip](https://pip.pypa.io/en/stable/)
[pip client](https://pip.pypa.io/en/stable/)

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Pip](#install-pip)
- [Verify Pip Version](#verify-pip-version)
- [Upgrade Pip](#upgrade-pip)
- [Install Package](#install-package)
- [Uninstall Package](#uninstall-package)
- [List Package](#list-package)
- [Download Package](#download-package)
- [Show Package](#show-package)
- [Search Package](#search-package)
- [Freeze Package](#freeze-package)





## Check Prerequisites

It is available together with the Python installation

 * Since Python 2 version 2.7.9
 * Since Python 3 version 3.4





## Install Pip

N/A





## >Verify Pip Version

Execute the following command via console

```bash
# For Python 2.X.X
pip --version
 
# For Python 3.X.X
pip3 --version
```





## Upgrade Pip

Execute the following command via console

```bash
# For Python 2.X.X
python -m pip install -U pip
 
# For Python 3.X.X
python3 -m pip3 install -U pip
```





## Install Package

Execute the following command via console

```bash
# Example 1
python -m pip install -U <package_name>

# Example 2
pip3 install <package_name>
```





## Uninstall Package

Execute the following command via console

```bash
# Example 1
python -m pip uninstall <package_name>

# Example 2
pip3 uninstall <package_name>
```





## List Package

Execute the following command via console

```bash
# Example 1
python -m pip list 

# Example 2 -o -> outdated packages
python -m pip list -o

# Example 3 -l -> only the packages in your current environment
python -m pip list -l
```





## Download Package

> Download packages from many different sources: Git, local project directories, remote archives, etc.

Execute the following command via console

```bash
# Example 1
python -m pip download [Options]

# Example 2
pip3 download [Options]
```





## Show Package

Execute the following command via console

```bash
# Example 1
python -m pip show packagename

# Example 2
pip3 show packagename
```





## Search Package

Execute the following command via console

```bash
# Example 1
python -m pip check

# Example 2
pip3 check
```




## Freeze Package

Execute the following command via console

```bash
# Example 1
python -m pip freeze -r requirements.txt

# Example 2
pip3 freeze -r requirements.txt
```

