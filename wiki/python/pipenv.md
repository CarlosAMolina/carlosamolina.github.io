** Table of contents **
- [Introduction](#introduction)
- [Installation](#installation)
- [Run an environment](#run_an_environment)
  - [New environment](#new_environment)
      - [Default virtualenv path](#new_environment_default_path)
      - [Custom virtualenv path](#new_environment_custom_path)
  - [Created environment](#created_environment)
      - [Show environments](#show_environments)
      - [Activate created virtual environment](#activate_created_virtual_environment)
- [Pipfile.lock: environment and packages](#pipfile_lock)
  - [Create a Pipfile.lock](#create_a_pipfile.lock)
      - [Install packages](#install_packages)
      - [Uninstall packages](#uninstall_packages)
      - [Lock environment](#lock_environment)
- [Exit virtual environment](#exit_virtual_environment)
  - [Error already activated](#error_already_activated)
- [Other commands](#other_commands)
- [Resources](#resources)

<a name="introduction"></a>
## Introduction

Pipenv is a command line tool to manage python virtual environments and pip installations.

<a name="installation"></a>
## Installation

```bash
pip install pipenv
```

<a name="run_an_environment"></a>
## Run an environment

<a name="new_environment"></a>
### New environment

<a name="new_environment_default_path"></a>
#### Default virtualenv path

With the following command, the desired python version is set too.

```bash
pipenv shell --python 3.7.2
```

Note. Its important to save the path of the environment in order to check later all available environments. Example:

```bash
✔ Successfully created virtual environment!                                                                    
Virtualenv location: /home/nonroot/.local/share/virtualenvs/nonroot-LcccbqV7                                   
Creating a Pipfile for this project…                                                                           
Launching subshell in virtual environment…                                                                     
 . /home/nonroot/.local/share/virtualenvs/nonroot-LcccbqV7/bin/activate                                        
nonroot@c3942b253696:~$  . /home/nonroot/.local/share/virtualenvs/nonroot-LcccbqV7/bin/activate
```

The location of the virtual environment can be checked too with the following command before exit the environment:

```bash
pipenv --venv
```

<a name="new_environment_custom_path"></a>
#### Custom virtualenv path

You can set the path of the venv:

```bash
export PIPENV_VENV_IN_PROJECT=1
pipenv shell --python 3.7.2
```

The venv will be created at the current location inside a .venv folder. Example: /home/nonroot/Documents/project/.venv/bin/activate

Remove the option:

```bash
unset PIPENV_VENV_IN_PROJECT
```

<a name="created_environment"></a>
### Created environment

You can work with a created virutal environment.

<a name="show_environments"></a>
#### Show environments

The location of the environments is showed when the first one was created. Example:

```bash
ls /home/nonroot/.local/share/virtualenvs/
```

<a name="activate_created_virtual_environment"></a>
#### Activate created virtual environment

If you are in the same path as your Pipfile and Pipfile.lock files:

```bash
pipenv shell
```

If you are in a different path, the path to the environment must be provided. Example:

```bash
source /home/nonroot/.local/share/virtualenvs/nonroot-LcccbqV7/bin/activate
```

<a name="pipfile_lock"></a>
## Pipfile.lock: environment packages

<a name="create_a_pipfile.lock"></a>
### Create a Pipfile.lock

The Pipfile.lock allows you to save the state of the environment and use later in other environment.

You have to install or uninstall packages and the lock the Pifile.lock file.

<a name="install_packages"></a>
#### Install packages

After start a pipenv shell:

```bash
pipenv install flask==0.12.1
```

Install from requirements files:

```bash
pipenv install -r requirements.txt
```

Install from Pipfile (omitting the dev section):

```bash
pipenv install
```

Install from Pipfile including the dev section:

```bash
pipenv install --dev
```

Install from Pipfile.lock. When you are in a virtual environment, the following command installs what's in the Pipfile.lock, ignoring the Pipfile.

```bash
pipenv install --ignore-pipfile
```

<a name="uninstall_packages"></a>
#### Uninstall packages

Only one package:

```bash
pipenv uninstall numpy
```

All packages:

```bash
pipenv uninstall -all
```

<a name="lock_environment"></a>
#### Lock environment

After install the packages (or uninstall them), we will create or update the Pipfile.lock file with all the information of the virtual environment.

```bash
pipenv lock
```

The Pipfile.lock file must not be modified, to do that, use the pipenv shell.


<a name="exit_virtual_environment"></a>
## Exit virtual environment

```bash
exit
```

If you are in a docker container, use the following option to avoid close the container:

```bash
CTRL-d
```

<a name="error_already_activated"></a>
### Error already activated

If you exit the environment using `deactivate` instead `exit`, you will have this error when you activate it again with `pipenv shell`:

```bash
Shell for UNKNOWN_VIRTUAL_ENVIRONMENT already activated.
No action taken to avoid nested environments.
```

The solution is simply to run the `exit` command (even though you are currently outside the vitual environment) and you will be able to activate the environment again:

```bash
exit
pipenv shell
```

Resource: <https://stackoverflow.com/questions/49944871/deactivate-a-pipenv-environment>.

<a name="other_commands"></a>
## Other commands

Location of the virtual environment:

```bash
pipenv --venv
```

<a name="resources"></a>
## Resources

- Activate and deactivate a virtualtual environment

  <https://github.com/pypa/pipenv/issues/84>

- Custom virtualenv path

  <https://github.com/pypa/pipenv/issues/1049>

- Documentation

  <https://pipenv-es.readthedocs.io/es/latest/>

- Pipenv install

  <https://pipenv.kennethreitz.org/en/latest/basics/#pipenv-install>

- Tutorial

  <https://realpython.com/pipenv-guide/#reader-comments>
