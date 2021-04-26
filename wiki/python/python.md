**Índice**

- [Codificación](#codificacion)
- [CPython](#cpython)
- [Decorator](#decorator)
- [Entorno virtuales](#venv)
- [Paréntesis](#parentesis)
- [Pip](#pip)
- [pipenv: pip y entornos virtuales](#pipenv)
- [pyenv: versión de python](#pyenv)

<a name=codificacion></a>
# Codificación

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
# CPython

https://moli.com.es/cpython/

<a name="decorator"></a>
# Decorator

https://realpython.com/primer-on-python-decorators/

<a name="venv"></a>
# Entorno virtuales

https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/

## Python 2

### Instalar

```bash
pip install virtualenv
```

### Crear

```bash
python -m virtualenv env
```

### Activar

```bash
source env/bin/activate
```
## Entornos virtuales y penv

Ver https://moli.com.es/pyenv/

<a name="parentesis"></a>
# Paréntesis

De no utilizar paréntesis, se tiene una referencia a la función, ejm:

```python
<function parent.<locals>.first_child at 0x7f599f1e2e18>
```

Con paréntesis: se llama al resultado de evaluar la función (llamar a la función de manera normal).

https://realpython.com/primer-on-python-decorators/

<a name="pip"></a>
# Pip

```bash
pip install -r requirements.txt
```

<a name="pipenv"></a>
# pipenv: pip y entornos virtuales

Para trabajar con pip y entornos virtuales, explicación en https://moli.com.es/pipenv/

<a name="pyenv"></a>
# pyenv: versión de python

Para instalar la versión deseada de python se utiliza pyenv. Explicado en: 
https://moli.com.es/pyenv/
