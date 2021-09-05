## Contenidos

- [Paths](#paths)
  - [plainnat.bst](#plainnatbst)
- [Caracteres no ASCII](#caracteres-no-ascii)
- [Formato](#formato)
  - [Orden apellido, nombre](#orden-apellido-nombre)
- [Ordenar alfabéticamente](#ordenar-alfabéticamente)
- [URLs](#urls)
  - [Mostrar URL](#mostrar-URL)
  - [Cortar URLs](#cortar-URLs)
- [Errores](#Errores)
  - [Texmaker muestra interrogación en lugar de número](#texmaker-muestra-interrogación-en-lugar-de-número)
  - [Al compilar siempre se tiene error](#al-compilar-siempre-se-tiene-error)

## Paths

### plainnat.bst

Ruta en Ubuntu a plainnat.bst: `/usr/share/texlive/texmf-dist/bibtex/bst/natbib`

## Caracteres no ASCII

Escribir del siguiente modo:
- Acentos: \'o -> ó
- letras mayúsculas: {P}
- ñ: \~n
- º: \textordmasculine{ } ({ } para que haya espacio después)

## Formato

### Orden apellido, nombre

Link <https://tex.stackexchange.com/questions/131087/displaying-authors-name-in-a-bibliographic-entry-in-the-form-surname-first-in>

## Ordenar alfabéticamente

Para ordenar alfabéticamente: escribir siempre el autor entre doble llave. Ejm `{{ xxx }}`.

## URLs

### Mostrar URL

Mostrar URL por ejemplo de un tipo @ article: 

- Importar paquete URL: `\usepackage{url}`
- Utilizar: `\bibliographystyle{plainurl}`

Link <https://tex.stackexchange.com/questions/21633/url-for-article-and-other-entries-of-the-bib-file>

### Cortar URLs

```bash
\usepackage[hyphens]{url}
\usepackage[hidelinks]{hyperref}
\hypersetup{breaklinks=true}
```

Link <https://tex.stackexchange.com/questions/115690/urls-in-bibliography-latex-not-breaking-line-as-expected>

## Errores

### Texmaker muestra interrogación en lugar de número

Menú `opciones` > `configurar texmaker` > `compilacion rapida`: `pdflatx+bi(la)tex+pdflatex(x2)+viewpdf`.

### Al compilar siempre se tiene error

Si nunca deja de aparecer un error, compilar solo la biografía (Bibtex), aunque de error, después compilar como siempre.