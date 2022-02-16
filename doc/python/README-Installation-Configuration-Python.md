# Installation / Configuration Python

Pythom execution engine running

[Python](https://www.python.org/)

>
>There are two different versions of Python :
>
> * Python 2.X.X. (No security support after 2020)
> * Python 3.X.X
>
>So keep in mind that they are two different "programs".
>
>An application written in one may NOT work in the other.
>
>Each minor version has 18 months of bugfix support and 5 years of security support.

Different distributions are available

 * *There are different ways to install it : Package installation, full installation, WSL (Windows),...*
 * *There are different distributions depending on the needs: IoT, computing, etc.*

System Python" is the Python that comes with or is installed on top of the operating system.

It is recommended to have pyenv installed as well Installation of pyenv

This type of installation presents problems when installing the same package globally with several versions.

https://stackabuse.com/install-python-on-mac-osx/





Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Verify Python Version](#verify-python-version)
- [Verify Python Installation Path](#verify-python-installation-path)
- [Install Python](#install-python)






## <a name="check-prerequisites">Check Prerequisites</a>

* ...





## <a name="verify-python-version">Verify Python Version</a>

Execute the following command via console

```bash
# For Python 2.X.X
$ python --version

$ python -V


# For Python 3.X.X
$ python3 --version

$ python3 -V


# From Code
$ python
Python 3.7.4 (default, Aug 13 2019, 15:17:50)
[Clang 4.0.1 (tags/RELEASE_401/final)] :: Anaconda, Inc. on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import sys
>>> sys.executable
'/Users/vjmadrid/Workspace/personal/python-lab/venv/bin/python'
```





## <a name="verify-python-installation-path">Verify Python Installation Path</a>

Execute the following command via console

```bash
# For Windows (with Powershell)
where.exe python

# For Linux / Mac
$ which python
```

Example result : /usr/bin/python




## <a name="install-python">Install Python</a>


### Installing Python on Windows

Ways : Microsoft package manager, full installation or WSL

**Full Installation for Windows**

Steps to follow :

1. Open your browser

2. Access the following URL 

 * https://www.python.org/downloads/
 * https://www.python.org/downloads/windows/

3. Locate the section "Python Releases for Windows"

4. Select the latest version available for Python 3 → 3.9.5

If it is not available, locate the version in the "Stable Release" section.

5. Select the installer version based on architecture : 64-bit or 32-bit

6. Run the installer

7. Verify that it has been installed correctly



### Installing Python on Mac


**Full Installation for Mac**

Steps to follow :

1. Open your browser

2. Access the following URL 

 * https://www.python.org/downloads/
 * https://www.python.org/downloads/mac-osx/

3. Locate the section "Python Releases for Mac OS X"

4. Select the latest version available for Python 3 → 3.9.5

If it is not available, locate the version in the "Stable Release" section.

5. Select the version of the installer according to OS version → macOS 64-bit installer

6. Run the installer

7. Run via console : pip3

8. Verify that it has been installed correctly



**HomeBrew Installation for Mac**

Steps to follow :

1. Open the console

2. Install HomeBrew if not already installed

3. Execute the command : 

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

4. Execute the command : brew upgrade (optional)

5. Execute the command : brew install python3

6. Execute the command : pip3

7. Verify that it has been installed correctly





### Installing Python on Linux

Ways : OS package manager and/or from the Python source code

Not all versions may be available for all operating systems, so it is advisable to install from the code

**Installation from Linux Manager**

Determine how it is done for each OS


**Code Installation for Linux**

Steps to follow :

1. Open your browser

2. Access the following URL 

* https://www.python.org/downloads/source/

3. Locate the section "Python Source Releases".

4. Select the latest version available for Python 3 → 3.9.5

If it is not available, locate the version in the "Stable Release" section.

5. Select the installer version → Gzipped source tarball

6. Download to your machine or get the URL to use the command line

7. Upgrade the system with the commands

 * Upgrade the package manager → sudo apt-get update
 * Upgrade the package manager → sudo apt-get upgrade
Install dependencies

```bash
# For apt-based systems (like Debian, Ubuntu, and Mint)
$ sudo apt-get install -y make build-essential libssl-dev zlib1g-dev \
       libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
       libncurses5-dev libncursesw5-dev xz-utils tk-dev

# For yum-based systems (like CentOS)
$ sudo yum -y groupinstall "Development Tools"
$ sudo yum -y install gcc openssl-devel bzip2-devel libffi-devel
```

8. Execute command :

```bash
$ tar xvf Python-3.X.X.tgz

$ cd Python-3.X.X

$ ./configure --enable-optimizations --with-ensurepip=install

$ make -j 8

$ sudo make altinstall
```

9. Verify that it has been installed correctly

