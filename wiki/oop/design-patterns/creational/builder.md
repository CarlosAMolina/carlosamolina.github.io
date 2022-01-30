## Contenidos

- [Motivación](#motivación)

## Motivación

Algunos objetos se crean de manera sencilla con una llamada de inicialización.

Otros objetos, necesitan unos requisitos previos y se acaba haciendo la llamada de inicialización con muchos argumentos, lo cual no es correcto.

`Builder` proporciona una manera de crear el objeto de manera sencilla.

## Ejemplo

Tienes código que convierto texto a formato HTML.

Primero, creamos una clase que pueda guardar todas las propiedades de un elemento HTML (indentación, texto, etc.), ejemplo `HtmlElement`.

Luego, creamos la clase builder, ejemplo `HtmlBuilder`, que se encargará de guardar el elemento HTML y los hijos que contenga (otros objetos de la clase `HtmlElement`). Esta clase se utilizará para crear los elementos HTML.

Código de ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/creational-patterns/builder/builder.py>

### Varios builders

A veces se requiere más de una clase builder. Ejemplo, una clase que guarde información de una persona, necesitará un builder que guarde datos de su lugar de residencia, otro builder para guardar datos de su trabajo, etc.

La idea es que, un clase builder base permita ir llamando al resto de builders.
