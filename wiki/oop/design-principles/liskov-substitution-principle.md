# Liskov Substitution Principle 

## Contenidos

- [Abreviatura](#abreviatura)
- [Definición](#definición)
- [Utilidad](#utilidad)
- [Ejemplo](#ejemplo)

## Abreviatura

- LSP: Liskov Substitution Principle 

## Definición

Una clase padre puede ser sustituida por cualquier otra clase que herede de ella y el programa debe seguir funcionando.

## Utilidad

Añadir nuevas funcionalidades sin tener que modificar las clases existentes.

Evita problemas a la hora de que el código escale.

## Ejemplo

Una clase que filtra productos por sus características, de no cumplir el principio, cada vez que se añada un nuevo criterio de filtrado hay que modificar la clase añadiendo nuevos métodos.

Para cumplir el principio, crearíamos clases que gestionen las características de los elementos y su filtrado, de modo que se pueden añadir nuevos criterios de filtrado sin modificar las clases existentes.

Código de ejemplo: <https://github.com/CarlosAMolina/design-principles>
