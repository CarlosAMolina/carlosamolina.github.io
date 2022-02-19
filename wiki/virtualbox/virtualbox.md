# VirtualBox

## Botones

- HOSTS: `control` (el de la derecha) + `c`

## Compartir carpetas entre VBox y host anfitrión

```bash
sudo mount -t vboxsf puenteW /root/Escritorio/puenteK
```

### Posibles errores

El primer paso para solucionarlos es actualizar VBox, el OS emulado, etc.

### Compartir archivos

Para pasar archivos entre la máquina virtual y el host anfitrión, los movemos a la carpeta del OS emulado en VBox donde se vea lo compartido con el anfitrión.

#### Máquina virtual con Windows

Tras crear la carpeta compartida, en la VM Windows buscar en la red (está en el menú izquierdo que aparece al abrir una carpeta donde salen listados otros directorios, mi ordenador, etc) la carpeta que se ha compartido.

#### Máquina virtual con Gnu/Linux
Tutorial: <https://www.youtube.com/watch?v=ddExu55cJOI>
1 utilizar Gest Additions: menú VirtualBox (desde maquina iniciada) > Dispositivos > insertar la imagen de CD de las "Gest Additions"
2 crear una carpeta en ubuntu (ubuntu es lo que hay corriendo en la maquina virtual)
3 compartir carpeta desde interfaz Vbox
4 en terminal de ubuntu: sudo mount -t vboxsf nombre_carpeta_en_windows ruta_carpeta_en_ubuntu
Ejm `sudo mount -t vboxsf puente /home/USERNAME/shareWindows`

tras esto todo lo que haya en la carpeta compartida de windows aparece en la carpeta utilizada en ubuntu y viceversa

nota: puente debe estar antes compartida en configuracion de Vbox (interfaz Vbox, fuera de la maquina corriendo) configuracion > Carpetas compartidas: seleccionarla)
nota 2: nombre_carpeta_en_windows es como termine la ruta compartida en la configuración de compartir carpetas de VirtualBox
nota 3: importante seleccionar una carpeta vacía ya que lo que haya en ruta_carpeta_en_ubuntu sera sustituido por el contenido de nombre_carpeta_en_windows. En caso de ocurrir esto no preocuparse, apagar Vbox y cerrar la aplicación de Vbox (dejarlo todo como antes de compartir carpetas, no se si es necesario quitar la carpeta compartida la configuración de la interfaz de VBox) y al encender todo estar como al principio

