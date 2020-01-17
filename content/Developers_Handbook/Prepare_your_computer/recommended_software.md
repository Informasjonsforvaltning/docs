---
title: Recommended software
weight: 3
description: A list of recommended software and how to install
---

### The following is a list of useful software that is recommended
#### An IDE
<a href="https://snapcraft.io/atom" target="_blank">ATOM</a>  
```
% sudo snap install atom --classic
```
or <a href="https://snapcraft.io/intellij-idea-community" target="_blank">IntelliJ IDEA Community Edition</a>
```
% sudo snap install intellij-idea-community --classic --edge
```
For Python-hackers, it is highly recommended to install and use <a href="https://gist.github.com/frfahim/73c0fad6350332cef7a653bcd762f08d" target="_blank">virtual-env</a>
```
sudo apt-get install python3-venv
```

#### Google Cloud SDK
```
sudo snap install google-cloud-sdk --classic
```
You then have to initialize the SDK. Follow instructions <a href="https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu" target="_blank">here</a>

#### kubectl
```
sudo snap install kubectl --classic
```
More <a href="https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux" target="_blank">here</a>

You need to set a default cluster (e.g fdk-dev) for kubectl commands:
```
gcloud container clusters get-credentials fdk-dev
```
#### Enable shell autocompletion for kubectl
In short, if you use zsh add the follwing line to the end of your ~/.zshrc file:
```
source <(kubectl completion zsh)
```
Instructions <a href="https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux" target="_blank">here</a>  
