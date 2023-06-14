<h1>Installation / Configuration NVM (Node Version Manager)</h1>




**Index**
- [Description](#description)
- [Requirements](#requirements)
- [Execution](#execution)
  - [Install NVM](#install-nvm)
  - [Set Node.js Version](#set-nodejs-version)
  - [Set Node.js Version .nvmrc File](#set-nodejs-version-nvmrc-file)
- [Authors](#authors)





## Description

Tool that allows you to install and configure the version of nodejs to work with (helps work / manage different versions and therefore manage different work environments)

[Node.js](https://nodejs.org)





## Requirements

* Check installed version

```bash
nvm version
```




## Execution

### Install NVM

Steps to follow:

* Installing a version of nodejs from nvm
* Set the version of node to work with


1. Access to the official website in the download area

[Node.js Download](https://nodejs.org/en/download/)



2. Run the following command to run version 8.10.0

```bash
nvm install 8.10.0

node --version
v8.10.0
```

Note : this way we make sure to have this version installed





### Set Node.js Version

If you have more than one version, you can choose which one to work with. In order to do this, all the identified installed versions will be shown and later it will be indicated which one to use.

1. Execute the following command

```bash
nvm list

    11.3.0
  * 10.14.1
    8.10.0

nvm use 8.10.0
...
nvm list

    11.3.0
    10.14.1
  * 8.10.0

```





### Set Node.js Version .nvmrc File

The configuration can be used from a configuration file : .nvmrc

Execute the following command in a directory next to that file

```bash
nvm use
```





## Authors

* **Víctor Madrid**