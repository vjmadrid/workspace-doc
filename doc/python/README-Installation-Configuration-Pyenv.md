# Installation / Configuration Pyenv

**pyenv** is a client-command tool for managing Python versions installations -> Python version manager 

[Web](https://github.com/pyenv/pyenv)

https://pythongranada.github.io/blog/pyenv.html

>**Important**
>
>* Avoid having to work with the System Python (Mac or Linux by default)
>
>The Mac operating system uses this install of Python (located in usr/bin/python) to perform critical tasks needed for the smooth operation of your computer (Python 2.7)

Featrues : 

* Allows install and manage multiple and different versions / distribution of Python on your system -> setup isolated python environment
* Works even if you have Python installed on your system previously
* Is a Bash extension and will not work on Windows outside of the Windows subsystem for Linux but exist a Win
* Reduces the problems of conflicting dependencies
* Allows to activate/change a version of Python : global or local
* Allows to activate different virtual environments
* Works very well with Mac → Install with homebrew
* Define, create and manage virtual environments (optional)
* Has plugins that add functionality pyenv-virtualenv, pyenv-doctor, etc.
* ...



>You are advised to check the Python installation path:
>
> * Run : which python
> * It is usually located in /usr/bin/python by default unless you are using a framework manager


Python Version Priority

1. pyenv shell -> $PYENV_VERSION
2. pyenv local -> .python-version file
3. pyenv global -> ~/.pyenv/version
4. system python


Documentación

https://github.com/pyenv/pyenv-installer

https://devguide.python.org/setup/#build-dependencies



Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Pyenv](#install-pyenv)
- [Verify Pyenv Version](#verify-pyenv-version)
- [Verify Pyenv Installation Path](#verify-pyenv-installation-path)
- [Load Values Shell](#load-values-shell)
- [Verify Available Managed Python Distributions](#verify-available-managed-pyhton-distribution)
- [Install Python Version](#install-python-version)
- [Verify Installations from Pyenv](#verify-installations-from-pyenv)
- [Uninstall Python Version](#uninstall-python-version)
- [Active Python Version](#active-python-version)
- [Verify Current Python Version](#verify-current-python-version)
- [Verify Current Python Version](#verify-current-python-version)





## Check Prerequisites

It is available together with the Python installation

* Since Python 2 version 2.7.9
* Since Python 3 version 3.4



**Verify Python Installation Path**

Execute the following command via console

```bash
# Windows (with powershell)
$ where.exe python

# Linux / Max
$ which python
```





## Install Pyenv

Certain operating system-dependent pre-installed system dependencies are required

**Pyenv support for Windows**

No native support for Windows

But basic support is available with : pyenv-win

https://github.com/pyenv-win/pyenv-win

https://github.com/pyenv-win/pyenv-win#installation


Create the folder in .pyenv/ in $HOME (c:\users/[user]\.pyenv)

Download the package https://github.com/pyenv-win/pyenv-win/archive/master.zip and unzip it in the above folder.

```bash
# Add PYENV and PYENV_HOME as environment variables
PS [System.Environment]::SetEnvironmentVariable('PYENV',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
PS [System.Environment]::SetEnvironmentVariable('PYENV_HOME',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")

# Add the folders to our user's PATH
PS [System.Environment]::SetEnvironmentVariable('path', $env:USERPROFILE + "\.pyenv\pyenv-win\bin;" + $env:USERPROFILE + "\.pyenv\pyenv-win\shims;" + [System.Environment]::GetEnvironmentVariable('path', "User"),"User")
```

**Pyenv support for Linux**

https://devguide.python.org/setup/#build-dependencies

https://github.com/pyenv/pyenv


**Pyenv support for Mac**

https://github.com/pyenv/pyenv#homebrew-on-macos

```bash
# Installing with Brew
$ brew install pyenv 

# Install dependencies
$ brew install openssl readline sqlite3 xz zlib
```





## Verify Pyenv Version

Execute the following command via console

```bash
$ pyenv --version
```





## Verify Pyenv Intallation Path

Execute the following command via console

Mac / Linux

```bash
$ which pyenv
```


Windows


```bash
PS (gcm pyenv).Path
```





## Load Values Shell

Execute the following command via console

```bash
# IMPORTANTE : Añadir parametros en .bashrc (.bash_profile en Mac o .zshrc)

# Load environment var PYENV_ROOT
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc

# Load environment var PYENV_ROOT en PATH
$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc

# Load initializer
$ echo 'eval "$(pyenv init --path)"' >> ~/.zshrc
$ echo 'eval "$(pyenv init -)"' >> ~/.zshrc

# 

$ echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc

# Reset ~/.zshrc
$ source ~/.zshrc

# Install dependencies -> associates
$ brew install openssl readline sqlite3 xz zlib
```

Other option 1

```bash
$ export PATH="$HOME/.pyenv/bin:$PATH"
$ export PATH="$PYENV_ROOT/bin:$PATH"

if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi
```

Other option  2

```bash
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

Other option 3

```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc
```





## Verify Available Managed Python Distributions

Shows all Python distributions available and usable.

* There are many versions and many distributions depending on your needs

```bash
# Show all Python  versions / distributions (CPython, etc.) -> Availables
$ pyenv install --list

# Show all Python 3.9.X versions / distributions
$ pyenv install --list | grep " 3\.[9]"
```





## Install Python Version

Execute the following command via console

```bash
# Install Python "3.9.4" version
$ pyenv install -v 3.9.4
```





## Verify Installations from Pyenv

The current distributions installed from pyevn are placed in other locations to facilitate their management

**Verify installed distributions from their own directories**

```bash
# Verify all installations
$ ls ~/.pyenv/versions/

# Verify Python 3.9.4 installation
$ ls ~/.pyenv/versions/3.9.4
```

They will be identified because they will be directory with the version name

**Verify installed versions from pyenv itself**

```bash
# Verify installations
$ pyenv versions
```

* The available versions will be shown and marked with a * the one that is active at that moment, which will coincide with the one triggered with "-V".
* The one indicated as "system" refers to the Python of the system.

```bash
# Verify version active
$ pyenv version
```





## Uninstall Python Version<

**Removing a distribution from pyenv**

Execute the following command via console

```bash
# Installed versions list
$ ls ~/.pyenv/versions/
 
# Remove installation
$ pyenv uninstall 3.9.4
```

* Select one of the facilities available from pyenv


**Removing a distribution from the installation directories**

Execute the following command via console

```bash
# Installed versions list
$ ls ~/.pyenv/versions/
 
# Remove installation
$ rm -rf ~/.pyenv/versions/3.9.4
```





## Active Python Version

**Global Activation**

Execute the following command via console

```bash
# Verify global installation -> Reference ~/.pyenv/version
$ pyenv global
 
# Activate global version python or change
$ pyenv global 3.9.4
 
# Verify active version with *
$ pyenv versions
 
# Verify active version (2)
$ python -V

# Verify active version (3)
$ cat ~/.pyenv/version

# Test
$ python -m test
```

Set the version you want to install from the available ones

**Local Activation**

Execute the following command via console

```bash
# Activate local version python or change -> Reference .python-version
$ pyenv local 3.9.4
 
# Verify active version with *
$ pyenv versions
 
# Verify active version (2)
$ python -V
```

Create a .python-version file in the current directory.
Enable this environment for this case

```bash

# Verify local active version 
cat .python-version
```





## Verify Current Python Version

Execute the following command via console

```bash
# Verificar que esta referenciada como la instalación de la maquina
$ cat ~/.pyenv/version
 
# Verificar version “current selected”
$ pyenv version

# Verify python pip version 
$ pyenv which python
```





## Verify Current Pip Path

Execute the following command via console

```bash
$ pyenv which pip
```

Show a path dependent on the active python version
