We will use pyenv to install an specific version of Python.

**Table of contents**

- [Requirements](#requirements)
- [Show available versions of Python](#show_available_versions_of_python)
- [Update pyenv](#update_pyenv)
- [Install a Python version](#install_a_python_version)
- [Remove a Python version](#remove_a_python_version)
- [Show installed Python versions](#show_installed_python_versions)
- [Activate a python version](#activate_a_python_version)
- [Show activated Python versions](#show_activated_python_versions)
- [Virtual environment](#virtual_environment)
- [References](#references)

<a name="requirements"></a>
## Requirements

### System dependencies.

As pyenv installs Python by building from source:

```bash
# Debian.
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl
```

### Install pyenv.

```bash
curl https://pyenv.run | bash
```

Specify a custom installation path:

```bash
export PYENV_ROOT="/home/nonroot/.pyenv"
curl https://pyenv.run | bash
```

References:

https://github.com/pyenv/pyenv-virtualenv/issues/53

### Add pyenv to the system path.

This sections follows the steps that the previous command shows at the end of its output.

- Edit ~/.bashrc.

```bash
vim ~/.bashrc
```

Add do the end of the file:

```bash
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
# Automatically activate a virtual environment when selecting one.
eval "$(pyenv virtualenv-init -)"
```

Reload the shell:

```bash
exec "$SHELL" # Or just restart your terminal
```

<a name="show_available_versions_of_python"></a>
## Show available versions of Python

Example, see CPython versions 3.6 through 3.8:

```bash
pyenv install --list | grep " 3\.[678]"
```

<a name="update_pyenv"></a>
## Update pyenv

To get latests python versions.

```bash
pyenv update
```

<a name="install_a_python_version"></a>
## Install a Python version

```bash
pyenv install -v 3.7.2
```

The installations are available at: ~/.pyenv/versions/

<a name="remove_a_python_version"></a>
## Remove a Python version

```bash
pyenv uninstall 3.7.2
```

<a name="show_installed_python_versions"></a>
## Show installed Python versions

```bash
pyenv versions
```

The line with an '*' at the beginning is the active version (system is the version installed in your machine).

<a name="activate_a_python_version"></a>
## Activate a python version

After do the previous steps, it's recommended to close and open the terminal.

- Activate the version for all paths.

```bash
pyenv global 3.7.2
```

- Activate the version only for the current path.

```bash
pyenv local 3.7.2
```

<a name="show_activated_python_versions"></a>
## Show activated Python versions

There are multiple commands to check the active python version:

- pyenv versions: the line with a '*' at the beginning is the active version (system is the version installed in your machine).

- python -V

- pyenv version

- cat ~/.pyenv/version

<a name="virtual_environment"></a>
## Virtual environment

Work with virtual environments and pyenv is managed by 'pyenv-virtualenv', that was installed at previous steps.

- Create.

```bash
pyenv virtualenv $PYTHON_VERSION $ENVIRONMENT_NAME
```

A file called '.python-version' is created in the current directory, it contains the virtual environment.

- Activate and deactivate.

Select the virtual environment:

```bash
pyenv local $ENVIRONMENT_NAME
```

The virtual environment will automatically be activated because when the path was added, the following line was included:

```bash
eval "$(pyenv virtualenv-init -)
```

To deactivate the virtual environment, select the system environment:

```bash
pyenv local system
```

If the previous line was not added to ~/.bashrc, the virtual environment can be activated and deactivated with:

```bash
pyenv activate $ENVIRONMENT_NAME

pyenv deactivate
```

<a name="references"></a>
## References

https://github.com/pyenv/pyenv

https://realpython.com/intro-to-pyenv/

