# Installation / Configuration Kubectl

Javascript execution engine running on the server side

[Node.js](https://nodejs.org)

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Node.js](#installnode)
- [Install NP;](#installnpm)





## <a name="check-prerequisites">Check Prerequisites</a>

* ...





## <a name="installnode">Install Node.js</a>

1. Access to the official website in the download area

[Node.js Download](https://nodejs.org/en/download/)

2. Follow the installation steps depending on the platform used

3. Check the installed version

```bash
node --version
```







## <a name="installnpm">Install NPM</a>

npm (Node Package Manager) Tool to manage node packages/dependencies

[NPM](https://www.npmjs.com/)


>IMPORTANT: 
>* It is usually installed by default with the version of node
>* Requires version upgrades


1. Check installed version

```bash
npm --version
```

2. Reminder to install a dependency (most common)

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

3. Reminder to uninstall a dependency (most common)

```bash
# Uninstall the dependencies in the "dependencies" area of the package.json file in the local node_modules directory.
npm uninstall <dependence>

# Uninstall the dependencies in the "dependencies" area of the package.json file in the global node_modules directory.
npm uninstall <dependence> -g
```
