# Configuration Workstation Apps

List of apps to facilitate the development in the workstation Environment

Step to follow:

* Check Prerequisites
* List of Apps

## Check Prerequisites

* N/A




## List of Apps



### Brew

- [Brew](https://brew.sh/) - MacOs Package Management

Installation

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```





### Core

* List of applications installed with Brew

Installation

```bash
# Brew install apps
brew install --cask firefox
brew install --cask skype
brew install --cask google-chrome

brew install coreutils
brew install curl
brew install git
brew install gpg
```





### Terminal

- [iTerm](https://iterm2.com/) - Mac Terminal Emulator

Installation

```bash
# Brew install
brew install --cask iterm2
```




### Z Shell

- [Zsh](http://www.zsh.org/) - Z Shell
- [Oh my Zsh](https://ohmyz.sh/) - Terminal Helper
    * [powerlevel9k](https://github.com/Powerlevel9k/powerlevel9k) - Theme for Zsh
    * [fzf](https://github.com/junegunn/fzf) - Command-line fuzzy finder

Installation

```bash
# Brew install
brew install fzf
```





### asdf-vm

- [Asdf-Vm](https://asdf-vm.com) - Gestor de versiones de plataforams

Installation

```bash
brew install asdf
```

Configuración para Zsh

```bash
echo -e "\n. $(brew --prefix asdf)/libexec/asdf.sh" >> ${ZDOTDIR:-~}/.zshrc
```

Installation of plugins

```bash
asdf plugin-add nodejs
asdf plugin-add java
asdf plugin-add python
```

Verify

```bash
# Number
asdf list all nodejs | wc -l

asdf list all nodejs

asdf install nodejs 16.20.2

asdf global nodejs 16.20.2
```

Updating plugins

```bash
asdf plugin update --all
```

```bash
asdf update       # via git
brew upgrade asdf # via homebrew
```





### IDE

- [Sublime](https://www.sublimetext.com/) - Text Editor

Installation

```bash
# Brew install
brew install --cask sublime-text
```

- [Visual Studio Code](https://code.visualstudio.com/) - Visual Studio Code Editor


Installation

```bash
# Brew install
brew install --cask visual-studio-code
```

**Personal**

```bash
# Importante
# * Decidir si se instala la ultima versión o bien se establece una concreta con @version

# **********************************
# Extensiones de VSC Personales

# Dracula Theme: Intefaz para reducir el cansancio de la vista
code --install-extension dracula-theme.theme-dracula --force
# Power Mode: Marca todo lo que puedes escribir en plan flipado
code --install-extension hoovercj.vscode-power-mode --force
```



**General**

```bash
# Importante
# * Decidir si se instala la ultima versión o bien se establece una concreta con @version

# **********************************
# Extensiones de VSC Generales : Mejorar la codificación

# Indent Rainbow: Facilita que la indentación sea más legible
code --install-extension oderwat.indent-rainbow --force
# Better Comments: Facilita hacer más legible los comentarios
code --install-extension aaron-bond.better-comments --force
# Prettier: Formateador de código que establece un estilo de código coherente
code --install-extension esbenp.prettier-vscode --force
# Prettigy JSON: Facilita hacer más legible los formatos JSON
code --install-extension mohsen1.prettify-json --force
# Trailing Spaces: Facilita la detección y eliminación de espacios extra en los textos / código
code --install-extension shardulm94.trailing-spaces --force
# Partial Diff: Facilita comparar dos secciones de texto / código
code --install-extension ryu1kn.partial-diff --force
# Rainbow Brackets: Facilita comparar dos secciones de texto / código
code --install-extension 2gua.rainbow-brackets --force
# XML Tools: Facilita el trabajar con formato XML, XQuery y XPath
code --install-extension DotJoshJohnson.xml --force
# YAML: Facilita el soporte a YAML
code --install-extension redhat.vscode-yaml --force
# Better Jinja: Soporte para Jinja2
code --install-extension samuelcolvin.jinjahtml --force


# **********************************
# Extensiones de VSC Generales : Markdown

# Markdown All in One: Facilita una serie de herramientas para trabajar con Markdowns
code --install-extension yzhang.markdown-all-in-one --force
# Markdownlint: Lintador y checkeador de estilo para Makdown
code --install-extension DavidAnson.vscode-markdownlint --force
# Markdown Preview Enhanced: Previsualizador de Markdown
code --install-extension shd101wyy.markdown-preview-enhanced --force
# Markdown PDF: Facilita la exportacion de Markdown a PDF, HTML, PNG, ...
code --install-extension yzane.markdown-pdf --force

# **********************************
# Extensiones de VSC Generales : Git

# Git Lens: Integra funcionalidades de Git sobre el Editor
code --install-extension eamodio.gitlens --force

# **********************************
# Extensiones de VSC Generales : Extra

# Open in Browser: Facilita abrir alguno de los elmentos desde un navegador
code --install-extension techer.open-in-browser --force
# Remote SSH: Facilita trabajar con servidores remotos o máquinas virtuales
code --install-extension ms-vscode-remote.remote-ssh --force
# Remote SSH Editing Files: Facilita trabajar con servidores remotos o máquinas virtuales desde un fichero de configuracion
code --install-extension ms-vscode-remote.remote-ssh-edit --force
# Material Icon Theme: Facilita un catalogo de iconos paras los diferentes ficheros
code --install-extension PKief.material-icon-theme --force
# REST Client: Proporciona un cliente para realizar peticiones HTTP desde VSC
code --install-extension humao.rest-client --force
# Draw.io Integration: Facilita la integración con Draw.io
code --install-extension hediet.vscode-drawio --force
# Live Share: Facilita la colaboración en tiempo real con otros desarrolladores
code --install-extension MS-vsliveshare.vsliveshare --force
# Code Snap: Facilita el realizar capturas de pantalla sobre el código
code --install-extension adpyke.codesnap --force
# Regex Previewer: Facilita el progra expresiones regulares
code --install-extension chrmarti.regex --force
```




    * [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
    * [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
    * [Intellicode](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode)
    * [Remote - Container](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
    * [settings-sync](https://marketplace.visualstudio.com/itemdetails?itemName=Shan.code-settings-sync)





### Development tools

```bash
# Brew install
brew install asdf
```

Configuration





### Other tools

```bash
# Brew install
```





- [Docker](https://www.docker.com/) - Container
- [Dash](https://kapeli.com/dash) - API documentation Browser and Code Snippet Manager
- [SdkMan](https://sdkman.io/) - Sofware Development Kit Manager (Java JDK,....)
- [Git Kraken](https://www.gitkraken.com/) - Git GUI Client
- [Virtual Box](https://www.virtualbox.org/) - Virtual Machine
- [DBeaver](https://dbeaver.io/) - Database Tool
- [Postman](https://www.getpostman.com/) - API Development Tool
- [minikube](https://github.com/kubernetes/minikube) - Implments Local Kubernetes cluster
- [vagrant](https://www.vagrantup.com/) - Development Environment Tool
- [Wine](https://www.winehq.org/) - Run Windows Application






## Authors

* **Víctor Madrid**