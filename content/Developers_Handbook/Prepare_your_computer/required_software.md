---
title: Required software
weight: 2
description: A list of required software and how to install
---

## In your linux machine you will need to install some software
#### Docker
Instructions [here](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
#### Docker compose
Instructions [here](https://docs.docker.com/compose/install/)
#### Maven
```
% sudo apt-get install maven
```
#### OpenJDK
```
% sudo apt-get install default-jdk
```
This is as of now openjdk-11. If you need java 8, do
```
% sudo apt-get install openjdk-8-jdk
```
#### Kotlin
```
% snap install kotlin
```
#### Git
```
% sudo apt-get install git
```
#### Python
Python (both 2.7 and 3.) should be preinstalled.
```
% python --version
Python 2.7.16+
% python3 --version
Python 3.7.4
```
#### NodeJS
It is highly recommended to use the _node version manager_ (`nvm`). To install nvm, follow [instructions](https://github.com/nvm-sh/nvm#installation-and-update).

Then, to download, compile, and install the latest release of node, do this:
```
% nvm install node # "node" is an alias for the latest version
```
