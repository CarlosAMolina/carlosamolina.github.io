## Contenidos

## Motivación

Añadir funcionalidades a una clase sin modificarla ni tener que heredar de ella.

Esto permite tener la nueva funcionalidad separada de la clase.

## Ejemplo

### Funcional decorator

Son decorators creados en Python específicos para este lenguaje, no son de uso general. 

Se utilizan añadiendo el decorador sobre la definición de la función, precedido de `@`.

Ejemplo medir el tiempo que dura una función: <https://github.com/CarlosAMolina/design-patterns/blob/main/structural-patterns/decorator/functional_decorators.py>.

### Classic decorator

En lugar de utilizar la sintaxis de Python para decorar (utilizando `@`), creamos una clase que será el decorador a la que le pasaremos el objeto a decorar.

Estas clases decoradoras presentan el inconveniente de que, desde el objeto decorado resultante, no podremos acceder a los métodos de la clase inicial que se ha decorado.

Ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/structural-patterns/decorator/oop_decorator.py>.
