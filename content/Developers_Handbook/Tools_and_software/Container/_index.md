---
title: Container
weight: 1
---

# Container Engine
We recommend using Podman as your container engine. Podman is rootless by design, which makes it a more secure solution. Its daemonless design removes the single point of failure created by Docker's central daemon.

Read more about [Podman](https://podman.io)

# Installation (Podman Desktop)
```bash
brew install podman
```

# Setup Podman container engine
On macOS and Windows, running the Podman container engine requires running a Linux virtual machine.

By default, Podman Desktop initializes a Podman machine with a standard configuration.

Consider creating a custom Podman machine to:

- Control the assigned resources: CPUs, memory, and disk size.
- Use a custom boot image.
- Use the rootful connection by default, for example to run Kind.
- (On Windows) Route the traffic through the network connection from your Windows session.

**Prerequisites**​

- The Podman executable is installed.

**Procedure**​

- Go to Settings > Resources.
- In the Podman tile, click Create new.
- In the Create a Podman machine screen:
 - Name: Enter a name, such as podman-machine-default.
 - CPU(s): Select the number of CPUs, e.g. 2.
 - Memory: Select the memory size, e.g. 2048 MiB
 - Disk size: Select the disk size, e.g. 20 GiB.
 - Image path (Optional): Select a bootable image containing a virtual machine with Podman.
 - Machine with root privileges: Enable to use the rootful connection by default. Required to use Kind on Windows.
 - (On Windows) User mode networking (traffic relayed by a user process):  - Enable to route the traffic through the network connection from your  - Windows session. Required to access resources behind your VPN connection.
 - Click Create

# Docker compose
Docker compose has more features than Podman compose and therefor the recommended tool for running compose files.

Install docker compose by executing the following:
```bash
brew install docker-compose
```

Podman compose will now using /opt/homebrew/bin/docker-compose instead.

# Linking Docker
Some test frameworks call the **docker** command. Becaus To resolve this we have to make a static link to the **podman** command.
Find the path to your podman binary:
```
which podman
```
and then replace the <path-to-your-podman-binary> below with your path and run the command:

```bash
sudo ln -s <path-to-your-podman-binary> /usr/local/bin/docker
```
