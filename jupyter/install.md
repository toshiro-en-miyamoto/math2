# Install Jupyter Lab

- [Installing packages with venv](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/)
- [Installing Jupyter](https://jupyter.org/install)
- [Spellchecking in Jupyter](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/nbextensions/spellchecker/README.html)
- [JupyterLab Git extension](https://github.com/jupyterlab/jupyterlab-git)
- [How to use JupyterLab Git extension](https://blog.reviewnb.com/jupyterlab-git-extension/)

## Python virtual environment

`venv` (for Python 3) allows you to manage separate package installations for different projects. It creates a *virtual* isolated Python installation.

### The latest stable Python

As of December 2024, the latest stable Python is 3.13.1. See [here](https://www.python.org/downloads/).

#### For Mac OS

Even the latest Command Line Tools provides a quite old Python:

```bash
~ % python3 --version                                             
Python 3.9.6
```

Let's install the latest stable with Homebrew:

```bash
~ % brew install python@3
```

As of December 2024, the command installs the following formula:

- ca-certificates/2024-11-26
- mpdecimal/4.0.0
- openssl@3/3.4.0
- python@3.13/3.13.1
- readline/8.2.13
- sqlite/3.47.2
- xz/5.6.3

Make sure that the `path` environment variable include `/usr/local/bin`. Now we have the latest stable Python:

```bash
~ % python3 --version
Python 3.13.1
```

### Creating a virtual environment

Create a virtual environment named `jupyter` under the `~/venv` directory:

```bash
~ % mkdir venv
~ % cd venv
venv % python3 -m venv jupyter
```

Since version 3.12, `venv` creates `.gitignore`:

```bash
venv % ls -al jupyter
total 16
drwxr-xr-x   7 user1 staff  224 Dec 24 14:08 .
drwxr-xr-x   3 user1 staff   96 Dec 24 14:08 ..
-rw-r--r--   1 user1 staff   69 Dec 24 14:08 .gitignore
drwxr-xr-x  12 user1 staff  384 Dec 24 14:08 bin
drwxr-xr-x   3 user1 staff   96 Dec 24 14:08 include
drwxr-xr-x   3 user1 staff   96 Dec 24 14:08 lib
-rw-r--r--   1 user1 staff  287 Dec 24 14:08 pyvenv.cfg

venv % cat jupyter/.gitignore
# Created by venv; see https://docs.python.org/3/library/venv.html
*

venv %
```

The `bin` directory of the virtual environment provides with one shell `activate` and two executables `pip` and `python`.

```bash
venv % ls -al jupyter/bin
total 72
drwxr-xr-x  12 user1 staff   384 Dec 24 14:08 .
drwxr-xr-x   7 user1 staff   224 Dec 24 14:08 ..
-rw-r--r--   1 user1 staff  9031 Dec  4 02:59 Activate.ps1
-rw-r--r--   1 user1 staff  2170 Dec 24 14:08 activate
-rw-r--r--   1 user1 staff   922 Dec 24 14:08 activate.csh
-rw-r--r--   1 user1 staff  2193 Dec 24 14:08 activate.fish
-rwxr-xr-x   1 user1 staff   247 Dec 24 14:08 pip
-rwxr-xr-x   1 user1 staff   247 Dec 24 14:08 pip3
-rwxr-xr-x   1 user1 staff   247 Dec 24 14:08 pip3.13
lrwxr-xr-x   1 user1 staff    10 Dec 24 14:08 python -> python3.13
lrwxr-xr-x   1 user1 staff    10 Dec 24 14:08 python3 -> python3.13
lrwxr-xr-x   1 user1 staff    41 Dec 24 14:08 python3.13 -> /usr/local/opt/python@3.13/bin/python3.13
```

### Using the virtual environment

The executables `python` and `pip` in the virtual environment can not be executed because the `bin` directory is not included in the path:

```bash
venv % which python
python not found

venv % which pip   
pip not found
```

Run the `activate` shell to add them to the path:

```bash
venv % source jupyter/bin/activate

(jupyter) venv % which python
~/venv/jupyter/bin/python

(jupyter) venv % which pip
~/venv/jupyter/bin/pip

(jupyter) venv % python --version
Python 3.13.1

(jupyter) venv % pip --version
pip 24.3.1 from ~/venv/jupyter/lib/python3.13/site-packages/pip (python 3.13)
```

You can exit the virtual environment by:

```bash
(jupyter) venv % deactivate
venv %
```

### Preparing `pip`

`pip` installed by `python3 -m venv` might not be up-to-date. Check the latest version of `pip` at [PyPi site](https://pypi.org/project/pip/).

You can make sure that `pip` is up-to-date by running:

```bash
(jupyter) venv % python -m pip install --upgrade pip
```

## Installing Jupyter Lab in the virtual environment

Beside Jupyter Lab, additional features are helpful:

- [Spell Checker NB extension](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/nbextensions/spellchecker/README.html)
- [`git` Python package for Jupyter Lab](https://github.com/jupyterlab/jupyterlab-git)

In order to the Spell Checker NB extension, you need to install the `jupyter_contrib_nbextensions` Python package.

```bash
(jupyter) venv % pip install --upgrade jupyterlab jupyterlab-git jupyter_contrib_nbextensions
```

The command installs the following Python packages:

- webencodings
- wcwidth
- pure-eval
- ptyprocess
- jupyter_highlight_selected_word
- ipython_genutils
- fastjsonschema
- websocket-client
- webcolors
- urllib3
- uri-template
- types-python-dateutil
- traitlets
- tornado
- tinycss2
- soupsieve
- sniffio
- smmap
- six
- setuptools
- send2trash
- rpds-py
- rfc3986-validator
- pyzmq
- pyyaml
- python-json-logger
- pygments
- pycparser
- psutil
- prompt_toolkit
- prometheus-client
- platformdirs
- pexpect
- parso
- pandocfilters
- packaging
- overrides
- nest-asyncio
- mistune
- MarkupSafe
- lxml
- jupyterlab-pygments
- jsonpointer
- json5
- idna
- h11
- fqdn
- executing
- defusedxml
- decorator
- debugpy
- colorama
- charset-normalizer
- certifi
- bleach
- babel
- attrs
- async-lru
- asttokens
- appnope
- terminado
- stack_data
- rfc3339-validator
- requests
- referencing
- python-dateutil
- matplotlib-inline
- jupyter-core
- jinja2
- jedi
- httpcore
- gitdb
- comm
- cffi
- beautifulsoup4
- anyio
- jupyter-server-terminals
- jupyter-client
- jsonschema-specifications
- ipython
- httpx
- gitpython
- arrow
- argon2-cffi-bindings
- jsonschema
- isoduration
- ipykernel
- argon2-cffi
- nbformat
- nbclient
- jupyter-events
- nbconvert
- jupyter-server
- notebook-shim
- jupyterlab-server
- jupyter-server-mathjax
- jupyter-lsp
- nbdime
- jupyterlab
- notebook
- jupyterlab-git
- jupyter_contrib_core
- jupyter_nbextensions_configurator
- jupyter_contrib_nbextensions

As you can see, the `matplotlib-inline` and `jupyter-server-mathjax` packages are installed along with Jupyter Lab.

### Commonly used Python packages

The following packages are commonly used:

```bash
(jupyter) venv % pip install --upgrade numpy pandas scikit-learn matplotlib seaborn jupyter
```

The following packages are installed along with the `jupyter` package:

- widgetsnbextension
- jupyterlab-widgets
- ipywidgets
- jupyter-console

The following packages are installed along with the `pandas` package:

- pytz
- tzdata

The following packages are installed along with the `scikit-learn` package:

- threadpoolctl
- scipy
- joblib

The following packages are installed along with the `matplotlib` package:

- pyparsing
- pillow
- kiwisolver
- fonttools
- cycler
- contourpy

## Other Python packages

### Mathematical packages

#### SymPy

[SymPy](https://docs.sympy.org/dev/index.html) is a Python library for symbolic mathematics. [It](https://docs.sympy.org/dev/tutorials/intro-tutorial/intro.html) can simplify expressions, compute derivatives, integrals, and limits, solve equations, work with matrices, and much, much more, and do it all symbolically.

```python
from sympy import *
x = symbols('x')
d = diff(sin(x)*exp(x), x)
assert d == exp(x)*sin(x) + exp(x)*cos(x)
```

The following command installs not only `sympy` but `mpmath`.

```bash
(jupyter) venv % pip install --upgrade sympy
```
