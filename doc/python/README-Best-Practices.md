READED

    * https://docs.python-guide.org/writing/structure/
    * https://kenreitz.org/essays/2013/01/27/repository-structure-and-python
    * https://medium.com/analytics-vidhya/structuring-python-code-best-practices-from-over-10-blogs-2e33cbb83c49

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


https://github.com/pypa/sampleproject/

https://antonz.org/python-packaging/

https://github.com/nalgeon/podsearch-py

https://github.com/nalgeon/podsearch-py/blob/main/Makefile

https://docs.python.org/3/howto/logging.html#logging-basic-tutorial

https://docs.python.org/3/howto/logging.html#logging-advanced-tutorial

EJEMPLOS DE CODIGO

* https://aaronluna.dev/categories/tutorial-series/
* https://aaronluna.dev/series/flask-api-tutorial/part-1/
* https://aaronluna.dev/blog/error-handling-python-result-class/
* https://github.com/a-luna/flask-api-tutorial/blob/master/src/flask_api_tutorial/api/auth/endpoints.py
* https://github.com/po5i/flask-mini-rest
* https://github.com/j2logo/tutorial-flask

* https://github.com/agusnavce/keycloak_example
* https://codefellows.github.io/sea-python-401d4/lectures/python_packaging_1.html#specifying-dependencies
* https://github.com/j2logo/tutorial-flask.git
* https://j2logo.com/tutorial-flask-leccion-7-parametros-de-configuracion-proyecto/#config-instance
* https://github.com/X1Zeth2X/flask-restx-boilerplate/
* https://github.com/tenable/flask-logging-demo
* https://github.com/Kinto/kinto/tree/master/kinto/core

# https://testdriven.io/blog/flask-pytest/

* https://flask-restx.readthedocs.io/en/latest/parsing.html
* https://marshmallow.readthedocs.io/en/stable/_modules/marshmallow/exceptions.html

* https://github.com/jonatasoli/example-flask-restx
* https://testdriven.io/blog/flask-pytest/

FLASK

* https://testdriven.io/blog/flask-contexts/
* https://testdriven.io/blog/flask-contexts-advanced/
* https://gitlab.com/patkennedy79/flask_user_management_example/-/blob/main/project/models.py





Requires specific:

* Build tools 
* Packagers
* Installers

All require specific versions
Problem 1: Python projects are very brittle system
Problem 2: juggling multiple build environment artifacts

## Package Management





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
