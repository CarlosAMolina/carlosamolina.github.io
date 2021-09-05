## Contenidos

- [Consideraciones](#Consideraciones)
  - [Espacio antes de la figura](#Espacio-antes-de-la-figura)
- [Recursos](#Recursos)

## Consideraciones

### Espacio antes de la figura

Al insertar una imagen no vale esto:

```bash
La siguiente imagen:

\\
\begin{figure}[H]
\includegraphics[width=\textwidth,height=\textheight,keepaspectratio]{./imagenes/image.jpg}
\end{figure}
```

Debe ser as�:

```bash
La siguiente imagen:
\\
\begin{figure}[H]
\includegraphics[width=\textwidth,height=\textheight,keepaspectratio]{./imagenes/image.jpg}
\end{figure}
```

## Recursos

Bordes

<http://tex.stackexchange.com/questions/20640/how-to-add-border-for-an-image>

Subfiguras

<http://tex.stackexchange.com/questions/55640/trying-to-put-a-box-around-a-collection-of-subfigures>

Tutorial im�genes

<https://es.sharelatex.com/learn/Inserting_Images#A.C3.B1adir_etiquetas.2C_leyendas_y_referencias>
