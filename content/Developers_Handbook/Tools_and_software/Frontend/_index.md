---
title: Frontend
weight: 2
---

## Front-end tools

- [Node.js](https://nodejs.org/en)
    - We use [nvm](https://github.com/nvm-sh/nvm?target=_blank) to manage our node/npm versions.

- [Yarn](https://yarnpkg.com/getting-started/install)
    - Our newer applications use Yarn, but older ones use [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) to build and install the dependencies

### Node versions < 15 on mac
To install node below 15 you need to do the following steps:
1. Open terminal in Rosetta2 mode: Go to Application -> Right click on terminal app -> Get Info -> Select "Open using Rosetta" -> Restart Terminal
2. In Terminal, write -> 
```bash 
arch -x86_64 zsh 
```
