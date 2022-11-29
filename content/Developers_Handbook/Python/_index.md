---
title: Python
weight: 9
---

- We use [pyenv](https://github.com/pyenv/pyenv) to manage python versions on our systems.
- We use [pipx](https://github.com/pypa/pipx) for installing cli apps.
- We use [poetry](https://python-poetry.org/), [nox](https://nox.thea.codes/en/stable/) and [nox-poetry](https://github.com/cjolowicz/nox-poetry) to manage dependencies and automate our testing. This stack is also used in our CI workflows.

Even though all of the tools are very well documented, there are things that you need to do once in a while that can be hard to remember.

The following is therefore a list of usefull things to know which is not easily found in the documentation.

__Update pyenv in order to install newer python__:

```Shell
% pyenv update
```

__List all packages and version-information__:

```Shell
% pipx runpip nox list
```

__Uninstall a package previously injected__:

```Shell
% pipx runpip nox uninstall nox-poetry
```

## References

- [Method definitions](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html)
- [Status Code Definitions](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)  
- [JSON Patch](https://tools.ietf.org/html/rfc6902)
- [Python Tutoial](https://www.scaler.com/topics/python/)
