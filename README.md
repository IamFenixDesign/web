# Feliz cumpleaños Isa

Web de cumpleaños con diseño estilo Windows 11. Cada sección es una **carpeta del escritorio** que se abre en su propia ventana:

| Ícono | Qué muestra | Carpeta del repositorio |
|---|---|---|
| Inicio | Es el fondo de la web (no una ventana): banderines en el borde superior, cartel "Feliz cumpleaños Isa", pastel con velas, globos y confeti. El botón de la casa en la barra minimiza las ventanas y vuelve a él | |
| Fotos | Las fotos de Isa | `fotos/` |
| Videos | Los videos | `videos/` |
| Dedicatorias | Las dedicatorias (archivos `.txt`) | `dedicatorias/` |
| Carta especial | Muestra directamente el sobre; al tocarlo, la carta se abre en pantalla completa (`carta.txt`) | `carta-especial/` |

Ya no hace falta ningún `lista.json`: la web lee sola los archivos de cada carpeta. En la página no existe la opción de subir archivos: solo se muestra lo que está guardado en las carpetas.

```
index.html
minijuegos.html        (la versión anterior con los minijuegos)
fotos/          tus fotos y videos
videos/         tus videos
dedicatorias/   archivos .txt
carta-especial/ carta.txt
```

## Cómo agregar archivos
Solo sube el archivo a su carpeta (por ejemplo, `fotos/foto1.jpg`). Aparece solo, ordenado por nombre, y el nombre que se ve sale del archivo (`con-las-amigas.jpg` → "Con las amigas").

- **Fotos y videos:** cualquier imagen (jpg, png, webp, gif, avif, svg) o video (mp4, webm, mov) que subas a `fotos/` o `videos/` se muestra solo, con su miniatura. Por la web de GitHub el límite es de 25 MB por archivo; con git llega a 100 MB.
- **Dedicatorias y carta:** archivos `.txt`. Separa los párrafos con una línea en blanco. Si el último párrafo empieza con `—`, se muestra como firma.

## Publicar en GitHub Pages
Repositorio: https://github.com/IamFenixDesign/web
Web publicada: **https://iamfenixdesign.github.io/web/**

1. Sube al repositorio todo el contenido de este zip, con sus carpetas.
2. Ve a **Settings > Pages**, elige **GitHub Actions** (o **Deploy from a branch**, rama **main**, carpeta **/ (root)**).
3. En uno o dos minutos la web estará en la dirección de arriba.

Al subir un archivo, la web lo muestra sola en uno o dos minutos, incluso con la web abierta: se revisa cada 30 segundos y sin recargar la página. La lista se obtiene de la API pública de GitHub (límite de 60 consultas por hora por visitante, más que suficiente para esta web).

## Abrir la web con doble clic (desde tu PC)
Un navegador no deja que una página lea sola las carpetas de tu PC; hay que darle permiso una vez:
1. Abre `index.html` y toca el botón **"Elegir la carpeta de la web"**. Elige la carpeta que contiene `index.html`, `fotos`, `videos`...
2. Listo: se muestran los archivos y, mientras la web esté abierta, se actualiza sola cada 30 segundos al agregar o quitar archivos. No hay que ejecutar nada más.
3. Al volver a abrir la web, el primer toque en cualquier parte pide de nuevo el permiso (o usa "Reconectar la carpeta"). Si el navegador ofrece "Permitir en cada visita", elígelo.
Funciona en Chrome, Edge y Opera.

## En GitHub Pages
Aquí no hay que dar ningún permiso: la web lee las carpetas del repositorio y se actualiza sola. El repositorio debe tener las carpetas con tus archivos (`fotos/foto1.jpg`, no solo `index.html`) y el `index.html` de esta versión. Al subir, usa "Add file > Upload files" y arrastra las carpetas completas. Pasados 1 o 2 minutos aparecen solas.

## De dónde sale el contenido
Todo lo que se ve sale únicamente de los archivos que están dentro de cada carpeta (`fotos/`, `videos/`, `dedicatorias/`, `carta-especial/`). La web ya no trae textos ni fotos de ejemplo guardados dentro de `index.html`: si borras `carta.txt` o `para-isa.txt`, dejan de verse.

## Cambiar de foto o video sin cerrar el visor
Al abrir una foto o un video puedes pasar al siguiente o al anterior con las flechas ← → del teclado, con los botones ‹ › a los lados, o deslizando el dedo (o el mouse) hacia la izquierda o la derecha. Al llegar al final vuelve al principio.
El fondo del visor se ajusta solo al tamaño de cada foto o video: una foto vertical abre un visor angosto y una horizontal uno ancho.
