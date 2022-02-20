## Contenidos


## Motivación

Se utiliza para inicializar un objeto una única vez.

Ejemplo, cuando la inicialización consume muchos recursos o requiere tiempo, con singleton evitamos que la inicialización ocurra más de una vez y siempre se usará la misma instancia.

## Tipos

### Singleton Allocator

Controlamos si un objeto ya se ha inicializado:

- No se ha inicializado, inicializamos el objeto.
- Sí se ha inicializado, devolvemos ese objeto inicializado.

## Ejemplo

### Ejemplo Singleton Allocator

Utilizaríamos el magic method `__new__`, pero si la clase tiene el método `__init__`, hay que tener cuidado porque, aunque se devuelva la misma instancia de la clase, el método `__init__` se ejecutará cada vez que se inicialice el objeto.

Código de ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/creational-patterns/singleton/singleton_allocator.py>
