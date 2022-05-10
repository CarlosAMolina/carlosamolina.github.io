## Motivación

Tener un objeto que represente una operación de modo que tiene toda la información para realizarla. Esto permite acciones como:

- Deshacer una asignación.
- Guardar logs de lo llevado a cabo.

Ejemplo de usos en GUI, al hacer o deshacer acciones, copiar al pulsar control+c, etc.

## Ejemplo

### Command

Tenemos una clase `BankAccount` que permite sacar o guardar dinero pero no guarda las operaciones realizadas. Crearemos una interfaz para realizar las operaciones de sacar o guardar dinero que permita guardar logs e incluso deshacer las operaciones.

Ejemplo <https://github.com/CarlosAMolina/design-patterns/blob/main/behavioral-patterns/command/command.py>.

