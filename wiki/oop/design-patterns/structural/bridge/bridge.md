## Contenidos


## Motivación

Su objetivo es conectar componentes mediante abstracciones.

Evita el `Cartesian product` complexity explosion, es decir, la creación de muchas clases, por ejemplo, tenemos una clase padre que puede trabajar de una manera A y otra B; además, esta clase funciona en Windows y Unix, acabaríamos con 4 clases: WindowsA, WindowsB, UnixA y WindowsB.

Para solucionar esto crearíamos una clase relacionada con la clase base pero que se encargue de crear las clases específicas de cada plataforma.

En resumen, un Bridge es un mecanismo que separa una interfaz de una implementación. De este modo, la interfaz y la implementación no dependen de una relación de herencia, sino que puede haber herencia y agregación en lugar de solamente referencias a otros componentes.

## Ejemplo


Código de ejemplo: <>.


