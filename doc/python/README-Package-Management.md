# Package Management

**package management** is the ability to install, configure, upgrade and uninstall a package and its dependencies (arrowly)

Typical problems :

* **Poor Environment Reproducibility :** the slightly different configurations across environments result in “works on my machine” issues and time wasted reproducing bugs -> delaying time to market
* **Supply Chain Security :** installing unsigned binaries with package managers is convenient, but risky. 
    * Building packages from source for multiple operating systems is painful, especially if they require linked C libraries
* **Choosing the Right Packages/ Versions :** how can you be sure you are always choosing the correct, approved open source components and versions required by your organization?
* **Fixing Vulnerabilities :** investigating vulnerabilities, patching/updating components and rebuilding environments are time and resource -> less time for coding

Ince however, package management is more broadly concerned with managing the development environment created by installing multiple packages against a specific version of a programming language on a specific version of an Operating System (OS)

Modern package management is concerned with solving : 

* the dependency
* environment management issues that arise from this combination of components, languages and OS’s that original package
managers were never designed to deal with

This includes :

* **Multiple Environments :** provides the ability to work with several projects on my local system even though each one requires a different version of the language and/or different versions of packages
* **Dependency Conflicts :** if one package requires version X of dependency Z, but another package
requires version Y, how can the conflict be resolved?
* **Reproducibility :** provides the ability for a project to be deployed and run consistently on other systems
    * Ensuring that your project can be deployed in a consistent, reproducible manner is a key goal for any
    software development team
    * Python’s requirements.txt and pipfile.lock files specify the exact versions of dependencies in your project.
    These files go a long way to ensuring consistent deployability, given a specific version of the programming
    language.  
    * Requirements.txt and pipfile.lock files can get out of sync as different developers on a team update
    their development environment for their own purposes.
    Even when all development team members are using identical Docker images or Virtual Machines
    (VMs) for their development environments, you still need to ensure that they have been built with
    the latest Python environment, and that all development environments are up to date.
    When developing on one OS but deploying on a different OS, you may be missing OS-level
    dependencies.
    DevOps is often left to resolve multiple conflicting code check-ins, leading to CI/CD environments
    that differ from development environments

## Choosing the Right Packages

“How can I ensure my developers are using only the approved set of
components/component versions?”

Approaches:

### Use a local “walled garden” repository of packages

which can severely limit developers that want to experiment with new packages and/or new versions since they are simply not available

Typically, the approval process for adding new components to the walled garden can be quite lengthy and/or complex

### Manually maintain a list of approved packages/versions

which can quickly get out of date

Use a third-party tool, which can help restrict use of packages that feature unapproved licenses and/or those that have a vulnerability

However, developers can still gain access to unapproved packages that meet these criteria



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


