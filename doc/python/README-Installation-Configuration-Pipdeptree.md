# Installation / Configuration Pipdeptree

**Pipdeptree** is a command-line tool for displaying installed Python packages in a dependency tree. 

* Visualize a dependency conflict but  not provide for resolution of the conflict
* Help making the hierarchy of packages and dependencies in an environment more understandable : global and virtual environment
* better than using the pip freeze and pip list commands, which only display packages in a flat list without showing which packages are top level and which are dependencies


 


Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Pipdeptree](#install-pipdeptree)
- [Verify Pipdeptree Version](#verify-version-pipdeptree)
- [Use Pipdeptree](#use-pipdeptree)




## Check Prerequisites

It is available together with the Python installation

 * Since Python 2 version 2.7.9
 * Since Python 3 version 3.4





## Install Pipdeptree

> Pipdeptree needs to be installed in the same virtual environment that it is to be used in

Execute the following command via console

```bash
# Example 1
pip install pipdeptree

# Example 2
pipenv install pipdeptree 
```





## Verify Pipdeptree Version

Execute the following command via console

```bash

```




## Use Pipdeptree

Execute the following command via console

```bash
# Example 1
pipdeptree

# Example 2
pipenv run pipdeptree
```