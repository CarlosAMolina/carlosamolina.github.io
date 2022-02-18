## Contenidos

- [Motivación](#motivación)
- [Ejemplo](#ejemplo)
  - [Prototype](#prototype)
  - [Prototype Factory](#prototype-factory)

## Motivación

Crear un objeto copiando otro en lugar de crearlo desde cero.

## Ejemplo

### Prototype 

Si dos objetos van a tener los mismos datos, debemos evitar hacer un reference assigment, porque al modificar un objeto también se modificaría el otro. El objeto final no debe referenciar al inicial.

Supongamos que tenemos una clase `address` para guardar datos de dirección (calle, ciudad, etc) y otra clase `Person` que tiene un atributo donde se guarda la dirección. Si hay dos personas con la misma dirección, no es correcto inicializar la dirección en una variable y pasárselo a cada clase persona, porque al modificar la dirección de una persona, también se modificará la dirección de la otra.

La solución es utilizar `copy.deepcopy` de modo que se copien recursivamente los atributos de un objeto en otro y cuando se modifiquen en un objeto el otro no se ve alterado.

Código de ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/creational-patterns/prototype/prototype.py>

### Prototype Factory

Código de ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/creational-patterns/prototype/prototype-factory.py>

