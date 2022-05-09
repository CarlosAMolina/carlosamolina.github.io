## Motivación

Es utilizado cuando hay un grupo de componentes que pueden procesar un evento. Por ejemplo, al pulsar un botón, el encargado de gestionar el evento puede ser el mismo botón, o el elemento caja padre en el que se encuentre, o la ventana en la que se encuentre, etc.

Se puede hacer que un componente pare la cadena de ejecución.

## Ejemplo

### Method chain

Tenemos un juego con una clase `Creature` y otra clase `CreatureModifier` que puede hacer cambios en el ataque y defensa de la criatura.

La clase `CreatureModifier` no realiza ninguna modificación, pero almacena y se utilizará para ir llamando a los modificadores que se aplicarán a `Creature`.

También, hay una clase `NoBonusesModifier` que, tras llamarla, impedirá que el resto de modificadores añadidos tengan efecto; es decir, corta la cadena.

Ejemplo <https://github.com/CarlosAMolina/design-patterns/blob/main/behavioral-patterns/chain-of-responsibility/method_chain.py>.

