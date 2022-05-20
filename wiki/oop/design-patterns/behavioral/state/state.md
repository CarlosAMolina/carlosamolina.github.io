## Motivación

Se trata de un patrón en el que el comportamiento de un objeto es determinado por su estado. El estado del objeto va cambiando.

Un constructor que maneja el estado y las transacciones es llamado state machine.

## Ejemplo

### Detectar el estado de un objeto

En este ejemplo vemos si una bombilla está encendida o apagada.

El ejemplo a continuación es un ejemplo clásico porque cada estado es una clase, y estas clases manejan la transición a otro estado.

Puntos negativos de este ejemplo es que puede resultar algo complejo el manejar la transacción de un estado a otro mediante las clases que hemos creado, sería mas sencillo hacerlo directamente con unos métodos `on` y `off`.

Ejemplo <https://github.com/CarlosAMolina/design-patterns/blob/main/behavioral-patterns/state/classic.py>.

