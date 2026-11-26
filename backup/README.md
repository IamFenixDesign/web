# Feliz cumpleaños Isa

Web de cumpleaños con diseño estilo Windows 11. Cada sección es una **carpeta del escritorio** que se abre en su propia ventana:

| Ícono | Qué muestra | Carpeta del repositorio |
|---|---|---|
| Inicio | Es el fondo de la web (no una ventana): banderines en el borde superior, cartel "Feliz cumpleaños Isa", pastel con velas, globos y confeti. El botón de la casa en la barra minimiza las ventanas y vuelve a él | |
| Fotos | Las fotos de Isa | `fotos/` |
| Videos | Los videos | `videos/` |
| Dedicatorias | Las dedicatorias (archivos `.txt`) | `dedicatorias/` |
| Carta especial | Muestra directamente el sobre; al tocarlo, la carta se abre en pantalla completa (`carta.txt`) | `carta-especial/` |
| Audio | Canción de fondo del reproductor de Inicio | `audio/` |

Ya no hace falta ningún `lista.json`: la web lee sola los archivos de cada carpeta. En la página no existe la opción de subir archivos: solo se muestra lo que está guardado en las carpetas.

```
index.html
minijuegos.html        (la versión anterior con los minijuegos)
fotos/          tus fotos y videos
videos/         tus videos
dedicatorias/   archivos .txt
carta-especial/ carta.txt
audio/          cancion.mp3
```

## Música del inicio
Coloca el archivo MP3 dentro de `audio/` con el nombre exacto `cancion.mp3` (`audio/cancion.mp3`). El reproductor de la pantalla de Inicio lo reproduce directamente en la web con los botones de Play y Pausa; ya no utiliza YouTube. No hace falta activar reproducción automática: el visitante toca Play para iniciar.

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
Todo lo que se ve sale únicamente de los archivos que están dentro de cada carpeta (`fotos/`, `videos/`, `dedicatorias/`, `carta-especial/` y `audio/`). La web ya no trae textos ni fotos de ejemplo guardados dentro de `index.html`: si borras `carta.txt` o `para-isa.txt`, dejan de verse.

## Cambiar de foto o video sin cerrar el visor
Al abrir una foto o un video puedes pasar al siguiente o al anterior con las flechas ← → del teclado, con los botones ‹ › a los lados, o deslizando el dedo (o el mouse) hacia la izquierda o la derecha. Al llegar al final vuelve al principio.
Las fotos y los videos siempre se abren en pantalla completa, con la imagen entera visible sobre fondo oscuro. Se cierran con la ✕ de arriba a la derecha o con Esc.

## Combinación de la carta especial
Al tocar el sobre se pide una combinación de 8 números. Solo con la correcta se abre la carta; si se falla, el teclado se sacude y se puede volver a intentar. Se pide cada vez que se toca el sobre. Se puede escribir con el teclado numérico o con los botones en pantalla.
Nota: es un candado de la experiencia, no una protección real. El archivo `carta-especial/carta.txt` sigue siendo público en el repositorio de GitHub, así que quien lo busque ahí puede leerlo sin la combinación.

## Confeti al abrir la web
Al abrir la web cae confeti por toda la pantalla y salen dos cañones desde las esquinas de abajo. Dura unos 7 segundos y se limpia solo. Al tocar el pastel sale otra ráfaga.

## Cuenta regresiva al 21 de diciembre
En la pantalla de inicio, bajo el saludo, hay una cuenta regresiva (días, horas, minutos y segundos) hasta el 21 de diciembre a las 00:00, con la hora del dispositivo de quien mira la web. Ese día el contador se reemplaza por "¡Hoy es el gran día!" y salen confetis: al abrir la web y una tanda nueva cada 9 segundos mientras siga abierta. Si la web está abierta cuando llegan las 00:00, el cambio ocurre solo. Pasado el 21, la cuenta apunta al 21 de diciembre del año siguiente.

## Música en la pantalla de Inicio
Coloca tus canciones (mp3, m4a, ogg, wav, flac...) en la carpeta `audio/`, con cualquier nombre: ya no hace falta que se llamen `cancion.mp3`. Se detectan solas, igual que las fotos.
- **Play/pausa:** toca o haz clic en el botón.
- **Elegir canción:** pasa el mouse por el botón y aparece la lista; en el celular, mantén el dedo sobre el botón y deslízalo hasta la canción (o toca una de la lista).
- **Al terminar:** si hay varias canciones pasa a la siguiente; si hay una sola, se repite.
