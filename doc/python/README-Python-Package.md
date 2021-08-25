# Python Pacakge

The phrase “Python Package” is an overloaded term, being associated with everything from .py files to .tar archives to .whl distributions. This quick read introduces the various ways that Python code has been made available for use, as well as how to work with them


## Types

No matter which type of package you prefer to work with, you should always build Python packages from source to ensure against compromised binaries



### Python Modules

Python is an interpreted language. As such, Python code is executed by an interpreter at runtime, rather than compiled into a binary as is the case with languages like C/C++. In its simplest form, Python code that performs some kind of function or method can be distributed as a module in the form of a text-based .py file.



### Python Libraries

The Python language itself ships with a standard set of libraries containing basic functions and methods. Libraries assemble collections of modules into a set of reusable code that developers can use to make more complex programs.



### Python Packages

Python code of any complexity typically requires multiple Python modules (or .py files) arranged in a hierarchy (e.g., foo.py calls bar.py, which calls baz.py) and contained in a directory structure. In order to preserve this directory structure, Python packages are typically shipped as .tar or .gz files called “source distribution packages,” or sdist for short. Because sdists only work with pure Python deployments in which you know which version of Python your environment supports, it’s largely been replaced by the more flexible wheel (.whl) distribution format.

You can add Python .tar and .gz packages to your environment with a simple pip install command, or else install them using a script. You can also uninstall Python packages using pip, as well




### Python Wheels

A .whl file (or wheel) is commonly referred to as a “built package” format. Wheels accomplish two goals:
    * Python Binary Distributions – Since interpreted code is typically slower than binary code, Python developers will sometimes incorporate routines written in C in order to speed up certain tasks. Wheels allow for the distribution of both precompiled binary code (for a specific OS) and the original source code (so users can compile it for their OS).
    * Python Built Distributions – Like most modern languages, Python supports modular development enabling developers to reuse existing code in their new codebase. A wheel ensures that all required code (typically located in multiple files) are distributed together

When you pip install a Python distribution that incorporates a wheel, pip will install all the files specified in the wheel



### Python Frameworks

Frameworks collect together a bundle of packages or modules that handle all the lower level functions required by a class of applications. For example, web frameworks bundle together packages that handle things like connection protocols, sockets and thread management in order to make web application development simpler. Frameworks are typically distributed in the .whl format.




### Python Egg

A **.egg file** is an old “built package” format for Python that bundles all the code, metadata and other required resources.

Note that the .egg format has largely been replaced by wheel. Attempting to install a .egg distribution with pip will likely fail. Instead, .egg files should be installed manually using Python’s setup tools (setup.py).




### Python Distributions

A distribution bundles together an implementation of the standard Python library, along with a number of third party packages, libraries and tools. There is a wide range of Python distributions (such as ActivePython or Anaconda) available from a variety of commercial vendors, organizations and developers


When installing or updating Python packages, it’s not uncommon to run into issues with permissions, incompatible libraries, and environments that suddenly become unusable. To avoid these kinds of pitfalls, there are a number of simple best practices you can follow to more easily manage your Python packages. 

Global or System-wide Installations – whenever possible, avoid relying on Python packages that are installed globally in an OS-dependent location for your projects (many operating systems install a system-wide version of Python by default). Issues that can arise with globally installed Python packages include:

* Dependency Conflicts – simply put, two different Python packages may rely on the same library, but not the same version of that library. Installing a Python package globally may overwrite an older version of a dependency, breaking Python packages that relied on the older version. To avoid dependency conflicts, use virtual environments (see below).
* Failed Installs – if you’re using Linux, the following is a typical scenario:
Python was installed using your Linux distibution’s native package manager (yum, apt, etc) to directories that require admin/root permissions to modify
If you use pip to install a Python package, either:
You’re logged in as a user so the install will fail since you don’t have admin/root permission, or
You’re logged in as root and overwrite, update or add new packages, which means your Python installation now differs from the native package manager’s records. If you subsequently use the native package manager to install a Python package, it will likely





## Virtual Environment Installations 

key best practice is to always create a new virtual environment for each and every project. For example:

python3.7 -m venv <env_name>
Virtual environments avoid dependency conflict issues that arise when you install a newer version of a Python package for your latest project that overwrites an existing version you still require for an older project. This happens because only one version of a Python package can be installed at a time for a given Python interpreter. Instead, always create a separate environment for each project in order to manage each project’s Python packages individually, minimizing version conflicts





## Python Package Versions

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