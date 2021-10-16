# Liskov Substitution Principle 

## Contenidos

- [Abreviatura](#abreviatura)
- [Definición](#definición)
- [Utilidad](#utilidad)
- [Ejemplo](#ejemplo)

## Abreviatura

- LSP: Liskov Substitution Principle 

## Definición

Una clase padre puede ser sustituida por cualquier otra clase que herede de ella y el programa debe seguir funcionando correctamente.

## Utilidad

Evitar resultados incorrectos por funciones que solo sean válidas para la clase padre y no para las hijas.

## Ejemplo

Tenemos una clase `Rectángulo` y otra `Cuadrado` que hereda de la primera. Estas clases tienen las propiedades `alto` y `ancho` pero, en el caso del cuadrado estos valores se igualan al modificar el otro.

También, las clases tienen un método para calcular el área multiplicando las propiedades `alto` y `ancho`.

Si un programa tiene una función que, guarda en una variable el valor de `alto` y luego calcula el área sin usar el método para ello, sino multiplicando la variable por un nuevo valor que se le vaya a dar a `ancho`, en el caso del cuadrado puede que no tenga en cuenta que `alto` y `ancho` deben valer igual y el resultado del área es incorrecto.

Es decir, tenemos una función que puede usarse para `Rectángulo` pero no para sus clases derivadas.

Solución:

- No usar la clase derivada `Cuadrado`, trabajar solo con `Rectángulo` añadiendo un flag que indique si es un cuadrado y un factory method que devuelva un rectángulo o un cuadrado. 
- De crear la clase `Cuadrado`, hacerlo sin los setters que igualan el ancho y el alto para evitar problemas con otras funciones.

Código de ejemplo: <https://github.com/CarlosAMolina/design-principles>
