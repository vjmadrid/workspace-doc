# Installation / Configuration Pipenv

pipenv - effectively combines pip+venv into a single tool that lets you create virtual environments
with whatever Python version you want, and then install and manage packages therein. It even
builds a dependency graph for your project, flagging any issues and generating a Pipfile.lock that
specifies every dependency and version in the project. You’ll need to manually denote
sub-dependencies, however, to ensure deterministic builds across platforms

Pipenv takes dependency management a step further than virtualenv. While the functionality is very similar to virtualenv, a few key features have been added to help limit some of the disadvantages of using virtualenv. The installation instructions can be found here.

https://pipenv.kennethreitz.org/en/latest/install/#installing-pipenv


Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Pipenv](#install-pipenv)
- [Verify Pipenv Version](#verify-pipenv-version)
- [Upgrade Pipenv](#upgrade-pipenv)




## Check Prerequisites

It is available together with the Python installation

 * Since Python 2 version 2.7.9
 * Since Python 3 version 3.4





## Install Pipenv

Execute the following command via console

```bash

```





## Verify Pipenv Version

Execute the following command via console

```bash
pipenv -version
```




## Upgrade Pipenv

Execute the following command via console

```bash
pip install –upgrade pipenv
```





## Use Pipenv

Execute the following command via console

To create a Pipenv project using Python 3.8, cd to the directory where you would like to create the project, then enter:

```bash
pipenv ENV

pipenv –python 3.8

pipenv install "SomePackage"
```

Pipfile & pipfile.lock: In addition to the Pipfile, pipenv generates a pipfile.lock that contains the exact version and source file hash of each package installed. This not only includes “SomePackage,” but also all the dependencies of “SomePackage.”

Pipfile.lock is an alternative to requirements.txt that improves upon the concept by including built-in dependency resolution. Pipfile.lock attempts to resolve any conflicts between packages – including their sub-dependencies – by loading package versions that satisfy all requirements.

If no solution exists, pipfile.lock cannot be created, and an error is output. This prevents the kinds of problems that arise from using requirements.txt, such as manually performing version control across dependencies and sub- dependencies.

Dependency Graph: When dealing with complex dependencies, it’s extremely helpful to be able to visualize how they relate. To that end, pipenv includes a method to visualize your dependencies:


pipenv graph



Dependency Management With Pipfile.Lock 
Whenever a package is installed in a pipenv environment, pipfile.lock is automatically updated to reflect dependency and sub-dependency changes. 

Depending on the circumstances, however, pipfile.lock may not update during package installation:

Pipfile.lock may fail to update during a package installation. For example, when cloning a repository made on another machine with a different OS, pipfile.lock may not update. Pipfile.lock incompatibilities can occur because the Pipfile.lock is system-specific.
      2. Large pipfile.lock files are very slow to update, and it may be practical to postpone the update. The pipenv install –skip-lock command option can be used to skip the pipfile.lock.

 If for any reason the pipfile.lock is not updated, the  pipenv lock command can be run to generate a new pipfile.lock file:  

$ pipenv install <packagename> 

# pipfile.lock will be updated.

$ pipenv install –skip-lock <packagename> 

# pipfile.lock will not update.

$ pipfile lock 

# a pipfile.lock will be generated.

Managing Dependencies With Venv
Venv is the successor to VirtualEnv, and functions in a similar manner with two important differences: 

Venv is included in Python 3.3+ and does not have to be installed.
Venv is a lower level tool than Pipenv, and is especially useful if Pipenv does not meet your particular virtual environment needs. 
If you are working with Python 3.8, you can create a Venv virtual environment by doing the following:

cd into the directory where you would like to create your project
Open a terminal or command window and enter:
$ python -m venv <project_directoryname>

If you are working with Python 3.7, you can create a Venv virtual environment by doing the following:

cd into the directory where you would like to create the project
Open a terminal or command window and enter:
$ python -m virtualenv venv <project_directoryname>

Managing Dependencies With Pyenv
Pyenv is a Python version manager that lets you do many tasks, including:

Change the global Python version
Install multiple Python versions
Set directory or project specific Python versions
Create and manage virtual environments.


