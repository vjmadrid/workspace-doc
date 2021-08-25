https://docs.python-guide.org/writing/structure/

https://kenreitz.org/essays/2013/01/27/repository-structure-and-python

https://medium.com/analytics-vidhya/structuring-python-code-best-practices-from-over-10-blogs-2e33cbb83c49

https://github.com/johnthagen/python-blueprint

https://data-flair.training/blogs/learn-python-notes/

https://choosealicense.com/

https://pythonhosted.org/an_example_pypi_project/setuptools.html

https://mitelman.engineering/blog/python-best-practice/automating-python-best-practices-for-a-new-project/

https://github.com/realpython/python-guide

https://github.com/bast/somepackage/blob/master/README.rst

https://the-hitchhikers-guide-to-packaging.readthedocs.io/en/latest/introduction.html

https://ellibrodepython.com/python-testing

https://docs.hektorprofe.net/python/distribucion/setuptools/

https://github.com/at-gmbh/at-python-template

https://github.com/jacebrowning/template-python

https://faun.pub/pyenv-multi-version-python-development-on-mac-578736fb91aa

https://mothergeo-py.readthedocs.io/en/latest/development/how-to/private-pypi.html

https://github.com/testdrivenio/private-pypi/blob/master/docker-compose.yml

https://testdriven.io/blog/private-pypi/

https://github.com/codekoala/docker-pypi/blob/master/entrypoint.sh

https://github.com/bmihelac/docker-images-with-private-python-packages-example

Requires specific:

* Build tools 
* Packagers
* Installers

All require specific versions
Problem 1: Python projects are very brittle system
Problem 2: juggling multiple build environment artifacts

## Package Management

package management is the ability to install, configure, upgrade and uninstall a package and its dependencies

* **Poor Environment Reproducibility :** slightly different configurations across environments result in “works on my machine” issues and time wasted reproducing bugs, delaying time to market.
* **Supply Chain Security :** installing unsigned binaries with package managers is convenient, but risky. On the other hand, building packages from source for multiple operating systems is painful, especially if they require linked C libraries.
* **Choosing the Right Packages/ Versions :** how can you be sure you are always choosing the correct, approved open source components and versions required by your organization? 
* **Fixing Vulnerabilities :** investigating vulnerabilities, patching/updating components and rebuilding environments are time and resource intensive, leaving less time for coding

As a Python programmer, you know that package management has been a work in progress for decades.
Defined narrowly, package management is the ability to install, configure, upgrade and uninstall a package
and its dependencies. In practice however, package management is more broadly concerned with
managing the development environment created by installing multiple packages against a specific version
of a programming language on a specific version of an Operating System (OS).

Modern package management is concerned with solving the dependency and environment management
issues that arise from this combination of components, languages and OS’s that original package
managers were never designed to deal with, including:

* **Multiple Environments :** how can I work with multiple projects on my local system if each requires
a different version of the language and/or different versions of packages?
* **Dependency Conflicts :** if one package requires version X of dependency Z, but another package
requires version Y, how can the conflict be resolved?
* **Reproducibility :** how can I ensure that my project can be consistently deployed and run on other
systems?
    * Ensuring that your project can be deployed in a consistent, reproducible manner is a key goal for any
    software development team
    * Python’s requirements.txt and pipfile.lock files specify the exact versions of dependencies in your project.
    These files go a long way to ensuring consistent deployability, given a specific version of the programming
    language 
    Requirements.txt and pipfile.lock files can get out of sync as different developers on a team update
    their development environment for their own purposes.
    Even when all development team members are using identical Docker images or Virtual Machines
    (VMs) for their development environments, you still need to ensure that they have been built with
    the latest Python environment, and that all development environments are up to date.
    When developing on one OS but deploying on a different OS, you may be missing OS-level
    dependencies.
    DevOps is often left to resolve multiple conflicting code check-ins, leading to CI/CD environments
    that differ from development environments

* **Choosing the Right Packages**

While not traditionally considered a package management issue, one of the most common problems we
hear from customers is, “How can I ensure my developers are using only the approved set of
components/component versions?”
Currently, most enterprises either:
The ActiveState Platform offers two approaches, depending on the enterprise’s needs:
Use a local “walled garden” repository of packages, which can severely limit developers that want
to experiment with new packages and/or new versions since they are simply not available.
Typically, the approval process for adding new components to the walled garden can be quite
lengthy and/or complex.
Manually maintain a list of approved packages/versions, which can quickly get out of date.
Use a third-party tool, which can help restrict use of packages that feature unapproved licenses
and/or those that have a vulnerability. However, developers can still gain access to unapproved
packages that meet these criteria.




While pip has long been the standard for installing and managing Python packages, it doesn’t address key
issues around environment and dependency management, such as creating and managing virtual
environments or dependency resolution. Numerous solutions have been introduced to try and bridge the
gap, including:

* venv
* virtualenv
* pipenv
* poetry

venv - built into the Python standard library since v3.3, venv provides support for creating and
managing virtual environments. You’ll still need to use pip to install and manage packages, though.






## Environment Management

managing the development environment created by installing multiple packages against a specific version of a programming language on a specific version of an Operating System (OS)

pip has been the standar for installing and managing Python packages
Require create anda manage virtual environment and / or dependecny resolution



## Update Python tools

    python -m pip install –upgrade pip setuptools




Tool for packagin and installation Python

Origin :

 * **distutils :** original Python packaging library tool that was first introduced in Python 1.6 and later deprecated in Python 3.10, but the **setup.py** standard it created still remains.
* **setuptools :** reuses setup.py, but incorporates requirements. Further, it provides an “easy_install” script, which acts as a package manager capable of both downloading and resolving dependencies from the Python Package Index (PyPI). 
    * These package management capabilities have been deprecated in favor of pip, leaving setuptools where it is today: Python’s foremost build front end. 
    * setuptools which doesn’t know how to build wheel files pip, which can only install wheel files
* **pip :** Tool provides Python with a package manager that uses setup.py and setuptools (use in background)

Problems :
* It assumes you have setuptools installed
* It’s missing key functionality that you would want from a true build front end, such as the ability to create sdist distributions


## setuptools 

Tools for package development process library and utility for building Python projects based on packages and their dependencies listed in a **setup.py** script


## Install manual package

* Download the package and extract it into a local directory.
* If the package includes its own set of installation instructions, they should be followed. Otherwise, the most common method for manually installing a package is to implement setup.py

### Installing Python Packages With Setup.Py
To install a package that includes a setup.py file, open a command or terminal window and: 

cd into the root directory where setup.py is located 

python setup.py install

### Setup.Py Build Environment

Packages installed with setup.py have build requirements that developers must adhere to. However, some requirements are optional

## Python Package 

The phrase “Python Package” is an overloaded term, being associated with everything from .py files to .tar archives to .whl distributions. This quick read introduces the various ways that Python code has been made available for use, as well as how to work with them

No matter which type of package you prefer to work with, you should always build Python packages from source to ensure against compromised binaries

* Python Modules – Python is an interpreted language. As such, Python code is executed by an interpreter at runtime, rather than compiled into a binary as is the case with languages like C/C++. In its simplest form, Python code that performs some kind of function or method can be distributed as a module in the form of a text-based .py file.
* Python Libraries – The Python language itself ships with a standard set of libraries containing basic functions and methods. Libraries assemble collections of modules into a set of reusable code that developers can use to make more complex programs.
* Python Packages – Python code of any complexity typically requires multiple Python modules (or .py files) arranged in a hierarchy (e.g., foo.py calls bar.py, which calls baz.py) and contained in a directory structure. In order to preserve this directory structure, Python packages are typically shipped as .tar or .gz files called “source distribution packages,” or sdist for short. Because sdists only work with pure Python deployments in which you know which version of Python your environment supports, it’s largely been replaced by the more flexible wheel (.whl) distribution format.

You can add Python .tar and .gz packages to your environment with a simple pip install command, or else install them using a script. You can also uninstall Python packages using pip, as well

* Python Wheels – A .whl file (or wheel) is commonly referred to as a “built package” format. Wheels accomplish two goals:
    * Python Binary Distributions – Since interpreted code is typically slower than binary code, Python developers will sometimes incorporate routines written in C in order to speed up certain tasks. Wheels allow for the distribution of both precompiled binary code (for a specific OS) and the original source code (so users can compile it for their OS).
    * Python Built Distributions – Like most modern languages, Python supports modular development enabling developers to reuse existing code in their new codebase. A wheel ensures that all required code (typically located in multiple files) are distributed together

When you pip install a Python distribution that incorporates a wheel, pip will install all the files specified in the wheel

* Python Frameworks – Frameworks collect together a bundle of packages or modules that handle all the lower level functions required by a class of applications. For example, web frameworks bundle together packages that handle things like connection protocols, sockets and thread management in order to make web application development simpler. Frameworks are typically distributed in the .whl format.
* Python Egg – a .egg file is an old “built package” format for Python that bundles all the code, metadata and other required resources.

Note that the .egg format has largely been replaced by wheel. Attempting to install a .egg distribution with pip will likely fail. Instead, .egg files should be installed manually using Python’s setup tools (setup.py).
* Python Distributions – A distribution bundles together an implementation of the standard Python library, along with a number of third party packages, libraries and tools. There is a wide range of Python distributions (such as ActivePython or Anaconda) available from a variety of commercial vendors, organizations and developers


When installing or updating Python packages, it’s not uncommon to run into issues with permissions, incompatible libraries, and environments that suddenly become unusable. To avoid these kinds of pitfalls, there are a number of simple best practices you can follow to more easily manage your Python packages. 

Global or System-wide Installations – whenever possible, avoid relying on Python packages that are installed globally in an OS-dependent location for your projects (many operating systems install a system-wide version of Python by default). Issues that can arise with globally installed Python packages include:

* Dependency Conflicts – simply put, two different Python packages may rely on the same library, but not the same version of that library. Installing a Python package globally may overwrite an older version of a dependency, breaking Python packages that relied on the older version. To avoid dependency conflicts, use virtual environments (see below).
* Failed Installs – if you’re using Linux, the following is a typical scenario:
Python was installed using your Linux distibution’s native package manager (yum, apt, etc) to directories that require admin/root permissions to modify
If you use pip to install a Python package, either:
You’re logged in as a user so the install will fail since you don’t have admin/root permission, or
You’re logged in as root and overwrite, update or add new packages, which means your Python installation now differs from the native package manager’s records. If you subsequently use the native package manager to install a Python package, it will likely

# Virtual Environment Installations 

key best practice is to always create a new virtual environment for each and every project. For example:

python3.7 -m venv <env_name>
Virtual environments avoid dependency conflict issues that arise when you install a newer version of a Python package for your latest project that overwrites an existing version you still require for an older project. This happens because only one version of a Python package can be installed at a time for a given Python interpreter. Instead, always create a separate environment for each project in order to manage each project’s Python packages individually, minimizing version conflicts

# Python Package Versions

Any well maintained Python package is constantly being upgraded and improved. The source code for the latest version of non-commercial packages can typically be found on Github/Gitlab, and the latest packaged version can be found on Python’s central repository, the Python Package Index (aka PyPI).

Python packages are typically updated in order to fix a critical bug or vulnerability. But when updating versions, care should be taken to ensure the environment is not compromised. Python provides the option to pin packages to a specific version in order to ensure it’s not accidentally updated. Most commonly, this is done in a requirements.txt file. 

The Python requirements.txt file is used to list all the packages incorporated in a Python project. In the requirements file, you can specify which package versions your project supports. For example:

Use == to pin a package to a specific version
Use >= to specify that a package can be updated
Non-pinned packages can be updated one at a time, or all at once across an entire environment or developer’s system

Managing Python Packages Better
As Python developers, we’re tired of the hassles Python package management leads to:

Managing dependencies and resolving conflicts by hand
Dealing with environment reproducibility and “works on my machine” issues
Maintaining and updating multiple tools and build environments
We love pip, as well as the myriad of other Python package managers that have been introduced to tackle the problems listed above. It’s just that they were never designed for modern Python development at scale. In this post, I’ll walk you through how we’ve fixed these headaches with the ActiveState Platform, but the TL;DR is:

Dependency management just got a lot easier – even for the hard cases
No complex setup or installs – builds are done from source in the cloud
Cross platform – same tools and commands on Linux and Windows (macOS soon)
Vulnerability remediation – find and fix vulnerabilities, even for transitive dependencies
Advanced features – virtual environments, versioning, rollbacks, branches, and more