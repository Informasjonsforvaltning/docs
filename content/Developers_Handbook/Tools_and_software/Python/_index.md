---
title: Python
weight: 4
---

# Setting up Python environment

Resources mentioned in this guide:
- **pyenv** ([github](https://github.com/pyenv/pyenv/))
- **poetry** ([homepage](https://python-poetry.org/))
- **nox** ([homepage](https://nox.thea.codes/))
- **nox-poetry** ([homepage](https://nox-poetry.readthedocs.io/))
- optional: **pipx** ([homepage](https://pipx.pypa.io/stable/))

## Installation and setup (macOS)
### Install pyenv ([docs](https://github.com/pyenv/pyenv?tab=readme-ov-file#installation))

On Mac OS X you need [Homebrew](https://brew.sh/) and the Xcode Command Line Tools:
```bash
xcode-select --install
```
Then run ([Pyenv suggested build environment](https://github.com/pyenv/pyenv/wiki#suggested-build-environment)):
```bash
brew install openssl readline sqlite3 xz zlib tcl-tk
```

Run the following commands:
```bash
brew update
brew install pyenv
```

Add the following lines to .zshrc:
```bash
export PYENV_ROOT="$(pyenv root)"
eval "$(pyenv init -)"
```

Check that installation was succesful:
```bash
pyenv --version
```
Should print the pyenv version, i.e. `pyenv 2.3.36`

To install the remaining packages and dependencies with the `pipx` CLI, continue reading Alternative A. For an alternative installation without `pipx` skip to Alternative B.

## Alternative A: Installation with `pipx`
### pipx
`pipx` is a CLI to install and run Python-applications in isolated environments. It is intended for globally available installations of Python CLIs, like Poetry, and not for libraries and project dependencies.

Note: pipx installed with brew is independent from the active python-version selected with pyenv.

### Install pipx ([installation-docs](https://pipx.pypa.io/stable/installation/))

To install, run the following commands:
```bash
brew update
brew install pipx
pipx ensurepath
```

Check that pipx is available:
```bash
pipx --version
```
Should print something like `1.4.3`.

Check that the line
```bash
export PATH="$PATH:/Users/<username>/.local/bin"
```
has been added to your `~/.zshrc` (or equivalent config file).

NB! Make sure that you are not in an active virtual environment (i.e. by running `poetry env use ...`) when running pipx commands. Otherwise pipx might install packages to the wrong virtual environment.

### Install Poetry with pipx ([installation-docs](https://python-poetry.org/docs/#installation))
Run:
```bash
pipx install poetry
```

Check that poetry is available:
```bash
poetry --version
```
This should print something like `Poetry (version 1.7.1)`

Make sure Poetry uses the currently active python version from pyenv by running:
```bash
poetry config virtualenvs.prefer-active-python true
```

When in a Poetry project with a pyproject.toml this should list a pyenv version of python:
```bash
poetry env info
```

### Nox
Nox is a command line tool that automates testing in multiple Python environments.

#### Install nox with pipx
```bash
pipx install nox
```

## nox-poetry
`nox-poetry` is a package which makes you able to run Poetry inside Nox sessions.

#### Install nox-poetry with pipx
To install it to the same environment as Nox is run from, run:
```bash
pipx inject nox nox-poetry
```

------

## Alternative B: Installation **without `pipx`**
Make sure you have the expected python version activated with `pyenv local x.x.x`, and make sure that `pip` is pointing to that python version.

This will install the packages for each python version. In other words you have to install the following packages for each python-version you install and activate with pyenv.

### Install Poetry
```bash
pip install poetry
```

Installing a specific version
```bash
pip install poetry==1.2.0
```

### Nox
```bash
pip install nox
```

### nox-poetry
```bash
pip install nox-poetry
```

-----

## Known problems
### VS Code can't find virtual environments
Make sure the project virtual environments created by Poetry are found by VS Code, by adding the following option to `settings.json` (macOS-specific):
```json
"python.venvPath": "~/Library/Caches/pypoetry/virtualenvs"
```
`poetry config virtualenvs.path` gives the venv-path on your on OS.

### Missing system library: lxml
Error message when running a nox session:
```bash
.cache/contract_tests-3-8/lib/python3.8/site-packages/feedgen/feed.py:17: in <module>
    from lxml import etree  # nosec - not using this for parsing
E   ImportError: dlopen(/Users/xxxx/Digdir/fdk-fulltext-search/.cache/contract_tests-3-8/lib/python3.8/site-packages/lxml/etree.cpython-38-darwin.so, 0x0002): symbol not found in flat namespace '_exsltDateXpathCtxtRegister'
```
Install the following packages:
```bash
brew install libxml2
brew install libxslt
```
We need to install an older version of lxml. Add the following line to your pyproject.toml.
```bash
lxml = "4.9.2"
```

### Docker command not found
When using podman and docker-compose it is possible you get the following error running tests:
```bash
Command: docker not found
```
Link podman to docker:
```bash
sudo ln -s /opt/podman/bin/podman /usr/local/bin/docker
```

## Podman/docker crashes
Remember to have setup enough resoures for your Podman machine.

## Useful commands

### pyenv
Install a specific Python version
```bash
pyenv install 3.11
```

Set the local python version for the current folder/project
```bash
pyenv local 3.11
```
This creates a `.python-version` file in the current directory.

Change python version globally (for user)
```bash
pyenv global 3.11
```
This is used as the default interpreter when no local python version is activated.
