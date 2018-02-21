---
layout: post
title: Pyenv & Virtualenv Cheat Sheet
excerpt: Condensed instructions on how to install and add the latest Android SDK to IntelliJ IDE on macOS
---

On macOS, you do not want to mess with the native Python. A good solution is to use **pyenv** which makes it possible to specify exactly which Python version you wish to run per directory.
```bash
  $ brew install pyenv                      # install pyenv with homebrew
  $ echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
  $ pyenv install --list                    # list all available versions of Python
  $ pyenv versions                          # list all currently installed Python versions, asteriks denotes the currently active Python version
  $ pyenv install <version number>          # install a desired version
  $ pyenv local <version number>            # specify a Python version for this current directory
```

It makes sense to maybe want certains pip packages of different versions in your Python projects. But how can this achieved? We know that with `pip install` packages are installed globally on your current Python version.
The solution to this is to use virtual environments. 