# Installation / Configuration Pip

**pip (pip installs packages)** is command-line interface (CLI) tool for the package management standard for Python

https://pip.pypa.io/en/stable/user_guide/

* Default / Standar tool for installation method for installing Python packages
* Has been part of the Python core language since Python 3.4 / 2.7.9.
* Pip can installs packages globally or it can install them for specific users
* Pip relies on a strong community-maintained package repository to install third party packages that are not included with your standard Python 3 installation
* Python modules available on the [Python Module Index](https://docs.python.org/3/py-modindex.html)
    * it automatically retrieves the package and all its dependencies from the Python Package Index (PyPI) and installs them locally on your system
* Provides diferent functions : install, uninstall and manage packages

[pip](https://pip.pypa.io/en/stable/)
[pip client](https://pip.pypa.io/en/stable/)

Requirements.Txt And Dependencies
Pip does not provide true dependency resolution, but this can be solved by using it in conjunction with a requirements.txt file. Requirements.txt files can be used to make pip resolve dependency conflicts between different packages.

The requirements.txt example below resolves a dependency conflict between two packages, where <package1> and <package2> require different versions of the same dependency.

If <package1> requires <package3==1.0> and <package2> requires <package3>=2.0, and if <package1> is resolved first, then Pip will use <package3>==1.0. In this scenario, a <package3> version that conflicts with <package2>‘s dependency requirement will be installed. The solution is to place <package3>=2.0 in the requirements.txt file together with the other requirements.


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
- [Package Upgrade Checklist](#package-upgrade-checklist)
- [Update All Packages](#update-all-packages)





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

pip install –upgrade pip
```





## Install Package

### Specific package

Execute the following command via console

```bash
# Example 1
python -m pip install -U <package_name>

# Example 2
pip3 install <package_name>

# Example 3
pip install "<package_name> == <version>"
```

### File package

Execute the following command via console

```bash
# Example 1
pip install -r requirements.txt

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




## Freeze PackagePackage Upgrade Checklist

Execute the following command via console

```bash
pip list --outdated
```

Upgrade outdated packages -> Depending on your operating system or virtual environment



## Update All Packages

Execute the following command via console

```bash
pip freeze > update-requirements.txt

pip install -r update-requirements.txt --upgrade
```


## Pip Subprocess

Create script file type 1

```bash
import sys
import subprocess

# Implement pip as a subprocess
subprocess.check_call([sys.executable, '-m', 'pip', 'install', '<packagename>'])
```


Create script file type 2

```bash
import sys
import subprocess

# Implement pip as a subprocess:
subprocess.check_call([sys.executable, '-m', 'pip', 'install','<packagename>'])

# Process output with an API in the subprocess module
reqs = subprocess.check_output([sys.executable, '-m', 'pip','freeze'])
installed_packages = [r.decode().split('==')[0] for r in reqs.split()]

print(installed_packages)

```

