<h1>Installation Depencies with Node</h1>





**Index**
- [Description](#description)
- [Requirements](#requirements)
- [Execution](#execution)
  - [Install Dependencies](#install-dependencies)
  - [Show Dependencies](#show-dependencies)
  - [Uninstall Dependencies](#uninstall-dependencies)
- [Authors](#authors)





## Description

In this procedure we will show you how to manage dependencies for Node





## Requirements

* Requires Node.js to be installed





## Execution

### Install Dependencies

Steps to follow:

1. Starting a terminal
2. Execute the following command

```bash
# Installation of the dependencies of the package.json file in the local node_modules directory
npm install

# Installation of the dependencies of the package.json file in the global node_modules directory
npm install -g

# Installation of the dependencies in the "dependencies" area of the package.json file
npm install <dependence>

# Installation of the dependency in the "devDependencies" area of the package.json file
npm install <dependence> --save-dev

# Installation of a dependency with a specific version
npm install <dependence>@<version>
```



### Show Dependencies

Steps to follow:

1. Starting a terminal
2. Execute the following command

```bash
npm list -g --depth 0
```



### Uninstall Dependencies

Steps to follow:

1. Starting a terminal
2. Execute the following command

```bash
# Uninstall the dependencies in the "dependencies" area of the package.json file in the local node_modules directory.
npm uninstall <dependence>

# Uninstall the dependencies in the "dependencies" area of the package.json file in the global node_modules directory.
npm uninstall <dependence> -g
```





## Authors

* **Víctor Madrid**