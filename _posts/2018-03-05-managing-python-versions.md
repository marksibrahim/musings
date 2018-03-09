---
layout:     post
title:      Managing Python Versions Effectively
date:       2018-03-04 12:32:18
summary:    setting up pyenv with pip, virtualenv, and Jupyter
---


After recently upgrading my homebrew, links to `python2` and `pip2` broke! 
I had no way to run different versions of Python. 
This left me searching for a more effective way to manage Python versions and dependencies. 

I discovered [pyenv](https://github.com/pyenv/pyenv), a great tool for specifying exact Python versions. 
It also integrates nicely with virtual environments and Jupyter!

## Setting Up Pyenv
1. Install pyven
```bash
brew install pyenv
```

2. Setup `.bash_profile` to configure and initialize pyenv
```bash
# pyenv for running specific python version
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
# initialize pyenv and virtualenv in shell
if command -v pyenv 1>/dev/null 2>&1; then  
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
fi
# show virtualenv changes in prompt
export PYENV_VIRTUALENV_DISABLE_PROMPT=1
```

## Using Pyenv

* Install a specific python version
```bash
$ pyenv install 2.7.10
$ pyenv install 3.5.0
$ pyenv versions
```

You can similarly uninstall a specific version using `uninstall`.

pyenv introduces three scopes for using python versions. It uses the first found in order of specificity: `shell`, `local`, and `global` (else defaults to system python).

* Set the **global** Python version
```bash
$ pyenv global 2.7.10
```

* Set the **local** version
```bash
$ pyenv local 3.10
# to remove
$ pyenv local --unset 
```
This creates a `.python-version` file in the directory. Pyenv automatically activates the local python version for all subdirectories:

* Shell overrides the python version for this **shell** session
```bash
$ pyenv shell 2.7.10
$ pyenv shell --unset
```

## Virtual Environments

Install [virtualenv plugin](https://github.com/pyenv/pyenv-virtualenv) for pyenv.

Use Homebrew: `brew install pyenv-virtualenv`

### Working with Virtual Environments

* Create a new virtual environment
```bash
$ pyenv virtualenv 2.7.10 my-project-2.7.10
```

This stores the virtualenv in a new directory `my-project-2.7.10` under `$(pyenv root)/versions/`---similar to virtualenvwrapper.

* Activate or deactivate
```bash
$ pyenv activate <name>
$ pyenv deactivate
```

## Pyenv and Jupyter

How do you setup Jupyter kernels for Python 2 and Python 3?

1. activate shell for each python version
`pyenv activate 2.7.14`
2. Install Jupyter 
`pip install jupyter`
3. Install Kernel
`python -m ipykernel install --user`

Et voila!
