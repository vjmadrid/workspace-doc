# Installation / Configuration Setup.py

**Setup.py** is the most important file. It's the file where define various aspects of your project are configured


Python file that relies only on the standard library can be redistributed and reused without the need to use setuptools.

* setup.py is the heart and center of Python projects installed with pip

Information included :

* **Project name :** enter a name for your project in quotes
* **Packages to include in the distribution :** the find_packages(‘,’) default argument will incorporate all packages that include an __init__.py file and are located in the local directory where setup.py is installed
* **Project version number :** enter a version number for the project in quotes
* **List a license for the project :** enter the name of the license you are licensing your project for use under in quotes
* **Short description of your library :** enter a brief description of your project in quotes
* **Long description of your library :** enter a more detailed description of your project either in text or using markdown
* **Your name :** enter your name in quotes to denote who the author is
* **Your email address :** optionally provide an email address in quotes where users can contact you
* **Link to your github repository or website :** optionally provide a link to your project’s repo
* **Download Link from where the project can be downloaded from :** provide an URL to your project’s source code in quotes
* **List of keywords :** – provide a list of keywords in square brackets associated with your project to make it easier to search for
* **List project dependencies :** provide a list of all the dependencies your project requires in square brackets. The easiest way to provide this is to copy and paste from the install_requires section (see below).
* **https://pypi.org/classifiers :** provide a list of all classifiers that apply to your project in square brackets. You can find a comprehensive list of classifiers at https://pypi.org/classifiers


To install a setup.py file including dependencies listed in install_inquires:

$ python setup.py install 



* Need to install setuptools


[setuptools](https://pypi.org/project/setuptools/)


Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Pip](#install-pip)





## Check Prerequisites

It is available together with the Python installation

 * Since Python 2 version 2.7.9
 * Since Python 3 version 3.4





## Install Pip

N/A





## Verify Pip Version

Execute the following command via console

```bash
# For Python 2.X.X
pip --version
```

