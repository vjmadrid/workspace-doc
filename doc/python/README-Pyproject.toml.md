# Use Pyproject.toml

**pyproject.toml** is the project definition file that is generated when you create a new project

TOML or Tom’s Obvious Minimal Language is a configuration file format similar to YAML

Pyproject.toml is just the Python implementation

Contains predictable build information about your project -> build your project

Multiple sections :

* **build-system :** specifies all the backend builder requirements, along with a backend entry point (API) at which you can just point your favourite build tool
* **project :** new section that’s not yet supported by all build tools, but supplies core metadata like the name and version for the project
* **tool.X :** you can optionally include specific information for specific build tools

pyproject.toml adds:

Flexible Builds – freely change how you build your project without disrupting your users.
Dependency Declaration – allows you to declare all of the dependencies that are required to start a build (such as Cython or Wheels)
Consumer Expectations – users and tools expect to be able to easily understand your project from a few key pieces of information.


For example, as Wheels have become more popular, using a pyproject.toml file makes it easy to build and install Wheels from your project since it’s tool agnostic

if you try to install source code with pip, you’ll get an obscure error message about a “bdist wheel” that can only be resolved (after searching on StackOverflow, or similar help forum) by installing Wheel from PyPI.

pyproject.toml is now a Python standard, meaning some projects won’t even work unless it’s included. In fact, more and more tools are adopting pyproject.toml as the location where they store their settings, even logging tools


- [Example Pyproject.toml File](#check-prerequisites)
- [Create Poetry Virtual Environment](#create-poetry-virtual-environment)





## Example Pyproject.toml File

Execute the following command via console

```bash
[tool.poetry]
name = “<projectname>”
version = “0.0.1”
description = “”
authors = [“Author Name <author@projecthame.com>”]

[tool.poetry.dependencies]
python = “^3.9”

[tool.poetry.dev-dependencies]
pytest = “^5.2”

[build-system]
requires = [“poetry>=0.12”]
build-backend = “poetry.acme.api”
```

Once a poetry project has been created, and dependencies added to pyproject.toml, a poetry.lock file (similar to a pipenv pipfile.lock) will be created to hold the dependency and sub-dependency details




## Create Poetry Virtual Environment

cd into the project directory

Execute the following command via console

```bash
poetry env use python
```