## Índice

- [Codificación](#codificacion)
- [CPython](#cpython)
- [Decorator](#decorator)
- [Entorno virtuales](#venv)
- [Paréntesis](#parentesis)
- [Pip](#pip)
- [pipenv: pip y entornos virtuales](#pipenv)
- [pyenv: versión de python](#pyenv)

<a name=codificacion></a>
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

<a name="cpython"></a>
## CPython

Ver [cpython](cpython.md).

<a name="decorator"></a>
## Decorator

https://realpython.com/primer-on-python-decorators/

<a name="venv"></a>
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
### Entornos virtuales y penv

Ver [pyenv](pyenv.md).

<a name="parentesis"></a>
## Paréntesis

De no utilizar paréntesis, se tiene una referencia a la función, ejm:

```python
<function parent.<locals>.first_child at 0x7f599f1e2e18>
```

Con paréntesis: se llama al resultado de evaluar la función (llamar a la función de manera normal).

https://realpython.com/primer-on-python-decorators/

<a name="pip"></a>
## Pip

```bash
pip install -r requirements.txt
```

<a name="pipenv"></a>
## pipenv: pip y entornos virtuales

Para trabajar con pip y entornos virtuales, explicación en [pipenv](pipenv.md).

<a name="pyenv"></a>
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

Es un gestor de versiones de Python, es parecido a pipenv pero para versiones de Python en lugar de paquetes pip.

Explicación en [pyenv](pyenv.md).

