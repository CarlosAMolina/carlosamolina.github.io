## Motivación

Iterar es acceder a los elementos de un objeto (lista, diccionario, etc.). El iterator es una clase externa utilizada para realizar esta iteracción.

Esta clase tiene una referencia al elemento actual y sabe cómo acceder a un elemento diferente.

Para implementarlo es necesario:

- `__iter__()`: para exponer el iterator.
- `__next__()`: para devolver cada uno de los elementos iterados.
- `raise StopIteration`: cuando no hay objetos con los que iterar.

## Ejemplo

### Tree transversal

Ejemplo <https://github.com/CarlosAMolina/design-patterns/blob/main/behavioral-patterns/iterator/tree_traversal.py>.

