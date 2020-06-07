# Istvan's EnV

This environment is based on the fantastic work of gantsign development environment with few changes.

Such as

* multi monitor support
* accelerate 2d settings support
* network card performance patch
* network performance patch
* clipboard-mode fix
* many more virtualbox tweaks

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/gantsign/development-environment/master/LICENSE)

A development environment for Java, Python, Node.js and Go built using Vagrant.

## Requirements

* Vagrant 2.2.x
* vagrant-hostsupdater or vagrant-hostmanager
* Virtualbox 6.1.x
* 4GB for the VM
* 2 CPUs for the VM

## Useful infos

### Kubernetes Dashboard 

Kubernetes [Dashboard](https://dashboard.localhost.com/) is available. You can generate a token 
with 

```bash 
microk8s kubectl -n kubernetes-dashboard describe secret admin-user-token | grep ^token
```

### Date Sync issues

```bash
sudo timedatectl set-ntp off && sudo timedatectl set-ntp on
```

### To make Chrome to trust the self sign certificate that was generated at build time add localhost.com cert using libnss3-tools

```bash 
[ -d ~/.pki/nssdb ] || mkdir -p ~/.pki/nssdb
certutil -d sql:$HOME/.pki/nssdb -A -n 'localhost.com cert authority' -i /etc/certs/localhost-ca.pem -t TCP,TCP,TCP
```

### If kubectl or kubeadm autocompletition does not work. They can be added manually 
To manually configure Zsh tab completion add the following to your .zshrc:

```bash
eval "$(kubectl completion zsh)"
eval "$(kubeadm completion zsh)"
```

## About

Getting your development environment setup correctly can be a time consuming and
error prone process; getting everyone on a team to setup their environment
correctly is even more challenging.

The goal of this project is to make setting up a development environment
reliable and reproducible. This project provides a generic development
environment that you can fork to add your project specific configuration.

## View the Website

[View the project website](https://gantsign.github.io/development-environment/)

## Project News

[View the latest project news](https://gantsign.github.io/development-environment/news/)

[Learn more about the requirements](https://gantsign.github.io/development-environment/docs/requirements)

## Feature Highlights

* Dynamically allocated swap space
* Compressed swap
* File backup & restore between rebuilds
* Terminator
* Oh My Zsh
* Docker
* Helm
* kops
* Visual Studio Code
* lazygit
* Git-GUI and Gitk
* Postman
* Open JDK
* Maven
* Maven Notifier
* IntelliJ IDEA IDE
* SDKMAN!
* Node.js
* Go language SDK
* Pyenv
* Pipenv


## License

MIT

## Author Information

Thank you 
(https://gantsign.github.io/development-environment/docs/requirements



