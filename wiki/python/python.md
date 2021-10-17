## Contenidos

- [Codificación](#codificación)
- [CPython](#cpython)
- [Decorator](#decorator)
- [Entorno virtuales](#entorno-virtuales)
  - [Python 2](#python-2)
  - [Python 3](#python-3)
  - [Entornos virtuales y penv](#entornos-virtuales-y-penv)
- [Paréntesis](#paréntesis)
- [Pip](#pip)
- [pipenv: pip y entornos virtuales](#pipenv-pip-y-entornos-virtuales)
- [Special methods](#special-methods)
- [Versión de python](#versión-de-python)
  - [De manera manual](#de-manera-manual)
  - [pyenv](#pyenv)

## Codificación

```python
# -*- coding: utf-8 -*-    
```

```python
a=u'Inglés'
print(str(a.encode('utf-8')))
Type: str -> Unicode
language.decode('utf-8')
```

## CPython

Ver [cpython](cpython.md).

## Decorator

https://realpython.com/primer-on-python-decorators/

## Entorno virtuales

https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/

### Python 2

#### Instalar

```bash
pip install virtualenv
```

#### Crear

```bash
python -m virtualenv env
```

#### Activar

```bash
source env/bin/activate
```

### Python 3

#### Instalar

```bash
pip install venv

# Segunda opción

sudo apt-get install python3-venv
```

#### Crear

```bash
python -m venv env
```

#### Activar

```bash
source env/bin/activate
```

### Entornos virtuales y penv

Ver [pyenv](pyenv.md).

## Paréntesis

De no utilizar paréntesis, se tiene una referencia a la función, ejm:

```python
<function parent.<locals>.first_child at 0x7f599f1e2e18>
```

Con paréntesis: se llama al resultado de evaluar la función (llamar a la función de manera normal).

https://realpython.com/primer-on-python-decorators/

## Pip

```bash
pip install -r requirements.txt
```

## pipenv: pip y entornos virtuales

Para trabajar con pip y entornos virtuales, explicación en [pipenv](pipenv.md).

## Special methods

Ver [special methods](special-methods.md).


## Versión de python

Podemos instalar diferentes versiones de Python en nuestro equipo, de manera manual o mediante un gestor de versiones.

### De manera manual

Primero, descargamos e instalamos la versión de Python deseada ([referencia](https://exitcode0.net/debian-10-how-to-upgrade-python-3-7-to-python-3-9/)). Ejemplo:

```bash
wget https://www.python.org/ftp/python/3.9.1/Python-3.9.1.tar.xz
tar xf Python-3.9.1.tar.xz
cd Python-3.9.1
./configure
make
make install 
```

Tras esto, indicamos al sistema que utilice esta versión de Python:

```bash
update-alternatives --install /usr/bin/python python /usr/local/bin/python3.9 10
```

Con el comando anterior configuramos que, al escribir `python` en la terminal, utilicemos la versión 3.9. Esto lo conseguimos mediante el uso de `update-alternatives`, más información sobre este comando en el siguiente [link](https://linuxhint.com/update_alternatives_ubuntu/).

### pyenv

Gestor de versiones de Python, es parecido a pipenv pero para versiones de Python en lugar de paquetes pip.

Explicación en [pyenv](pyenv.md).

