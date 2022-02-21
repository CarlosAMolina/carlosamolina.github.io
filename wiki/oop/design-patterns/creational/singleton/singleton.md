## Contenidos


## Motivación

Se utiliza para inicializar un objeto una única vez.

Ejemplo, cuando la inicialización consume muchos recursos o requiere tiempo, con singleton evitamos que la inicialización ocurra más de una vez y siempre se usará la misma instancia.

## Tipos

### Singleton Allocator

Controlamos si un objeto ya se ha inicializado:

- No se ha inicializado, inicializamos el objeto.
- Sí se ha inicializado, devolvemos ese objeto inicializado.

Se utiliza el magic method `__new__`, pero si la clase tiene el método `__init__`, hay que tener cuidado porque, aunque se devuelva la misma instancia de la clase, el método `__init__` se ejecutará cada vez que se inicialice el objeto.

### Singleton Decorator

Soluciona el problema de Singleton Allocator por el que se inicia el `__init__`.

### Singleton Metaclass

Igual que Singleton Decorator pero utiliza una clase intermedia en lugar de un decorator.

## Ejemplo

### Ejemplo Singleton Allocator

Código de ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/creational-patterns/singleton/singleton_allocator.py>

### Ejemplo Singleton Decorator

Código de ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/creational-patterns/singleton/singleton_decorator.py>

### Ejemplo Singleton Metaclass

Código de ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/creational-patterns/singleton/singleton_metaclass.py>

