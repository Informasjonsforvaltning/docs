---
title: Recommended software
weight: 3
description: A list of recommended software and how to install
---

### The following is a list of useful software that is recommended

#### An IDE

ATOM: <https://snapcraft.io/atom>

```Shell
% sudo snap install atom --classic
```

or IntelliJ IDEA Community Edition: <https://snapcraft.io/intellij-idea-community>

```Shell
% sudo snap install intellij-idea-community --classic --edge
```

For Python-hackers, it is highly recommended to install and use [virtual-env](https://gist.github.com/frfahim/73c0fad6350332cef7a653bcd762f08d)

```Shell
sudo apt-get install python3-venv
```

#### PyCharm

For Python-hackers using [PyCharm](https://www.jetbrains.com/pycharm/):

##### plugin

Add the poetry plugin <https://plugins.jetbrains.com/plugin/14307-poetry>

##### interpreter

- Ctrl+Alt+S -> Project -> python interpreter -> cog by dropdown -> Add -> Poetry Environment -> choose python interpreter, i.e. 'python3.9', from '.../.pyenv/shims/' as Base interpreter, and
- set 'poetry' from '.../.pyenv/shims/' as Poetry executable.

##### pytest

Ctrl+Alt+S -> Tools -> Python integrated tools -> Testing -> set 'pytest' as Default test runner

#### Google Cloud SDK

```Shell
sudo snap install google-cloud-sdk --classic
```

You then have to initialize the SDK. Follow instructions [here](https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu)

#### kubectl

```Shell
sudo snap install kubectl --classic
```

More [here](<https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux>

You need to set a default cluster (e.g fdk-dev) for kubectl commands:

```Shell
gcloud container clusters get-credentials fdk-dev
```

#### Enable shell autocompletion for kubectl

In short, if you use zsh add the follwing line to the end of your ~/.zshrc file:

```Shell
source <(kubectl completion zsh)
```

Instructions [here](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux)
