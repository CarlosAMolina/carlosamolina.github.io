## Motivación

Facilitar comunicación entre componentes sin que estos tengan que preocuparse unos de otros o tener una referencia directa entre sí.

Esto ayuda por ejemplo en casos en que objetos dejan de estar activos (ejemplo, un chat donde la gente se conecta y desconecta) ya que sería muy difícil mantener la relación.

## Ejemplo

### Chat room

Clase `ChatRoom` es el mediator, clases `Person` no tienen relación unas con otras.

Ejemplo <https://github.com/CarlosAMolina/design-patterns/blob/main/behavioral-patterns/iterator/tree_traversal.py>.

