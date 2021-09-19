# Open-Closed Principle 

## Contenidos

- [Abreviatura](#abreviatura)
- [Definición](#definición)
- [Utilidad](#utilidad)
- [Ejemplo](#ejemplo)

## Abreviatura

- OCP: Open-Closed Principle

## Definición

Clases deben ser abiertas para extensión, pero cerradas para modificación.

Es decir, nuevas funcionalidades deben añadirse con nuevas clases (por extensión), no modificando la clase o clases existentes.

## Utilidad

Añadir nuevas funcionalidades sin tener que modificar las clases existentes.

Evita problemas a la hora de que el código escale.

## Ejemplo

Una clase que filtra productos por sus características, de no cumplir el principio, cada vez que se añada un nuevo criterio de filtrado hay que modificar la clase añadiendo nuevos métodos.

Al cumplir el principio, se pueden añadir nuevos criterios de filtrado sin modificar las clases existentes.

Código de ejemplo: <https://github.com/CarlosAMolina/design-principles>
