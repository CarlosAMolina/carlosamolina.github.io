En esta entrada vemos cómo utilizar algunas opciones de DirBuster.

## Índice

- [Preparar el laboratorio](#preparar-el-laboratorio)
- [Setup inicial](#setup-inicial)
  - [Setup inicial DirBuster](#setup-inicial-dirbuster)
  - [Setup inicial OWASP ZAP](#setup-inicial-owasp-zap)
- [Opciones descubrimiento DirBuster](#opciones-descubrimiento-dirbuster)
  - [`Brute force files` desactivada](#brute-force-files-desactivada)
  - [Opciones `Brute force files` y `Use Blank Extention` seleccionadas, `File extention` sin valor](#opciones-brute-force-files-y-use-blank-extention-seleccionadas-file-extention-sin-valor)
  - [`Brute force files` seleccionada, `Use Blank Extention` no seleccionada y `File extention` con valor](#brute-force-files-seleccionada-use-blank-extention-no-seleccionada-y-file-extention-con-valor)
  - [Opciones `Brute force files` y `Use Blank Extention` seleccionadas y `File extention` con valor](#opciones-brute-force-files-y-use-blank-extention-seleccionadas-y-file-extention-con-valor)
- [Recursos](#recursos)

<a name="#preparar-el-laboratorio"></a>
## Preparar el laboratorio

- OS máquina física: Debian Stretch.
- Servidor: Apache. Instalación: `apt-get install apache2 apache2-mod-php7.0`.
- Software: DirBuster-0.12 y OWASP ZAP 2.7.0.

Lanzar servidor Apache con `/etc/init.d/apache2 start`.

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/servidor-apache-welcome-page.png)
> Imagen. Servidor Apache iniciado

Iniciar DirBuster:

```bash
java -jar ~/Documentos/dirbuster/DirBuster-0.9.12/DirBuster-0.0.12.jar
```

<a name="#setup-inicial"></a>
### Setup inicial 

<a name="#setup-inicial-dirbuster"></a>
#### Setup inicial DirBuster

- Target URL: http://127.0.0.1:80
- File with list of dirs/files: /home/x/Documentos/dirbuster/DirBuster-0.9.12/test.txt
- Work Method: Use GET requests only

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-configuracion-inicial.png)
> Imagen. DirBuster configuración inicial

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/diccionario-utilizado.png)
> Imagen. Diccionario utilizado

También, configuramos en DirBuster como proxy la dirección de OWASP ZAP para ver las peticiones que realiza:

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-configuracion-proxy.png)
> Imagen. DirBuster configuración proxy

<a name="#setup-inicial-owasp-zap"></a>
#### Setup inicial OWASP ZAP

- Menú herramientas > opciones… > Local proxies
- Address: 127.0.0.1
- Puerto: 8081

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/owasp-zap-configuracion-proxy.png)
> Imagen. OWAS ZAP configuración proxy

<a name="#opciones-descubrimiento-dirbuster"></a>
## Opciones descubrimiento DirBuster

En este apartado se analizan las opciones referentes al descubrimiento de archivos, sin incluir a los directorios, por lo que se analiza la ruta principal del servidor.

- Brute force files

    Opción para trabajar con los archivos indicados en el diccionario utilizado, en este caso test.txt.

    Para que DirBuster funcione, por lo menos debe estar seleccionada una de las opciones `Brute Force Dirs` o `Brute force files`.

- Use Blank Extention

    Buscar los archivos del diccionario.

- File extention

    Buscar los archivos en el diccionario pero añadiéndoles la extensión especificada. En los siguientes apartados esto se ve gracias a ZAP proxy.

<a name="#brute-force-files-desactivada"></a>
### `Brute force files` desactivada

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-dirs-configuracion.png)
> Imagen. DirBuster configuración

En este caso, no importan las opciones ‘Use Blank Extention’ ni ‘File extention’ puesto que el programa tratará las palabras del diccionario como si fueran directorios que buscar.

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-dirs-peticiones.png)
> Imagen. OWAS ZAP peticiones de DirBuster

Se observa que DisBuster ha añadido otros archivos y directorios además de los indicados en el diccionario, como ‘manual’ o ‘icons’.

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-dirs-resultados.png)
> Imagen. DirBuster resultados

<a name="#opciones-brute-force-files-y-use-blank-extention-seleccionadas-file-extention-sin-valor"></a>
### Opciones `Brute force files` y `Use Blank Extention` seleccionadas, `File extention` sin valor

Al utilizarse la opción `Brute force files`, ya no es necesaria la de `Brute Force Dirs` para que el programa funcione.

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-use-blank-extension-configuracion.png)
> Imagen. DirBuster configuración

De los archivos que hay en el diccionario, indica los existentes en la ruta principal del servidor.

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-use-blank-extension-peticiones.png)
> Imagen. OWAS ZAP peticiones de DirBuster

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-use-blank-extension-resultados.png)
> Imagen. DirBuster resultados

Se observa que DirBuster busca algunos directorios por defecto, como `icons`.

<a name="#brute-force-files-seleccionada-use-blank-extention-no-seleccionada-y-file-extention-con-valor"></a>
### `Brute force files` seleccionada, `Use Blank Extention` no seleccionada y `File extention` con valor

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-file-extention-configuracion.png)
> Imagen. DirBuster configuración

Lo indicado en `File Extention` se añade al final de los archivos del diccionario.

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-file-extention-peticiones.png)
> Imagen. OWAS ZAP peticiones de DirBuster

En este caso, en el servidor no existen los archivos buscados:

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-file-extention-resultados.png)
> Imagen. DirBuster resultados

<a name="#opciones-brute-force-files-y-use-blank-extention-seleccionadas-y-file-extention-con-valor"></a>
### Opciones `Brute force files` y `Use Blank Extention` seleccionadas y `File extention` con valor

Se buscan los archivo del diccionario como se han especificado en él y añadiéndoles la extensión descrita.

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-use-blank-extention-file-extention-configuracion.png)
> Imagen. DirBuster configuración

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-use-blank-extention-file-extention-peticiones.png)
> Imagen. OWAS ZAP peticiones de DirBuster

![](https://carlosamolina-public.s3.eu-west-1.amazonaws.com/wiki/dirbuster/dirbuster-brute-force-files-use-blank-extention-file-extention-resultados.png)
> Imagen. DirBuster resultados

<a name="#recursos"></a>
## Recursos

Instalar Apache

https://librematica.es/blogs/como-instalar-servidor-lamp-debian-9-stretch

DirBuster descarga

https://www.owasp.org/index.php/Category:OWASP_DirBuster_Project/es

OWASP ZAP descarga

https://github.com/zaproxy/zaproxy/wiki/Downloads
