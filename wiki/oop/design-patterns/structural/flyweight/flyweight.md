## Motivación

Está enfocado a optimizar la memoria almacenada.

En lugar de guardar las características de los objetos en ellos, se guardan en un objeto externo y se hace referencia a él, de este modo se ahorra espacio para objetos con las misas características al no tener que ir repitiendo la misma información.

## Ejemplo

### Usernames

En un videojuego, hay muchos usuarios con el mismo nombre, en lugar de almacenarlos todos, porque se irán repitiendo, guardamos una lista de strings únicos y para guardar cada usuario usamos índices a esa lista de strings.

Ejemplo: <https://github.com/CarlosAMolina/design-patterns/blob/main/structural-patterns/flyweight/users.py>.
