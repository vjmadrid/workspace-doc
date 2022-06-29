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
* https://blog.miguelgrinberg.com/post/handling-file-uploads-with-flask/page/0

https://github.com/pingidentity/pingone-sample-python/blob/master/services/auth.py

https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx/
https://www.geeksforgeeks.org/load-balancing-flask-application-using-nginx-and-docker/
https://www.patricksoftwareblog.com/how-to-configure-nginx-for-a-flask-web-application/
https://www.patricksoftwareblog.com/


flake8 : wrapper around Pyflakes, pycodestyle y McCabe
    * https://github.com/DmytroLitvinov/awesome-flake8-extensions
pep8-naming : PEP-8 naming conventions
isort : used to automatically separate imports in your code into the following groups:
    * 1standard library
    * third-party
    * local

    python -m isort .
    python -m isort my_module.py --check-only
flake8-black
flake8-bandit
safety
     safety check

We used pytest's monkeypatch fixture to replace all calls to the get method from the requests module with the lambda callback that always returns an instance of MockedResponse.

We used an object because requests returns a Response object.

We can simplify the tests with the create_autospec method from the unittest.mock module. This method creates a mock object with the same properties and methods as the object passed as a parameter:

Although pytest recommends the monkeypatch approach for mocking, the pytest-mock extension and the vanilla unittest.mock library from the standard library are fine approaches as well.

Another important aspect of tests is code coverage. It's a metric which tells you the ratio between the number of lines executed during test runs and the total number of all lines in your code base. We can use the pytest-cov plugin for this, which integrates Coverage.py with pytest.

Once installed, to run tests with coverage reporting, add the --cov option like so:

Mutation Testing helps ensure that your tests actually cover the full behavior of your code. Put another way, it analyzes the effectiveness or robustness of your test suite. During mutation testing, a tool iterates through each line of your source code, making small changes (called mutations) that should break your code. After each mutation, the tool runs your unit tests and checks whether your tests fail or not. If your tests still pass, then your code didn't survive the mutation test.

mutmut is a mutation testing library for Python. Let's look at it in action.

$ mutmut run --paths-to-mutate reject_loan.py --tests-dir=.

Some examples:

pytest-django - provides a set of tools made specifically for testing Django applications
pytest-xdist - is used to run tests in parallel
pytest-cov - adds code coverage support
pytest-instafail - shows failures and errors immediately instead of waiting until the end of a run
For a full list of plugins, check out Plugin List from the docs.

Type Checking
Tests are code, and they should be treated as such. Like your business code, you need to maintain and refactor them. You may even have to deal with bugs from time to time. Because of this, it's a good practice to keep your tests short, simple, and straight to the point. You should also take care not to over test your code.

Runtime (or dynamic) type checkers, like Typeguard and pydantic, can help to minimize the number of tests. Let's take a look at an example of this with pydantic.

hadolint:
	@ ./test/linting/lint.sh hadolint

shellcheck:
	@ ./test/linting/lint.sh shellcheck

eclint:
	@ ./test/linting/lint.sh eclint


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
