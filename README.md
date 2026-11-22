# 🎲 Minijuego del día

Una web con un minijuego distinto cada día (del 21 de noviembre al 4 de diciembre de 2026). Cada día se desbloquea con la fecha real y el último día hay una tarjeta de rasca y gana con el premio.

Es una sola página (`index.html`), sin dependencias ni build: solo HTML, CSS y JavaScript.

## 🚀 Publicar en GitHub Pages

Repositorio: https://github.com/IamFenixDesign/web
Web publicada: **https://iamfenixdesign.github.io/web/**

### Actualizar los archivos (desde la web de GitHub)
1. Abre el repositorio y entra a `index.html`, pulsa el lápiz ✏️ (o **Add file → Upload files**) y reemplázalo por el `index.html` nuevo. Haz lo mismo con `README.md`.
2. Confirma con **Commit changes** directo a la rama `main`.

### Actualizar los archivos (con git)
```bash
git clone https://github.com/IamFenixDesign/web.git
cd web
# copia aquí el index.html y el README.md nuevos
git add .
git commit -m "Actualizar minijuego"
git push origin main
```

### Activar GitHub Pages (solo la primera vez)
1. Ve a **Settings → Pages**.
2. En **Build and deployment**, elige **Deploy from a branch**, rama **main** y carpeta **/ (root)**. Guarda.
3. Espera 1 o 2 minutos y abre https://iamfenixdesign.github.io/web/

## ✏️ Cómo personalizarlo
Todo está en `index.html`, dentro de la etiqueta `<script>`:
- **Fechas:** las constantes `Y`, `M` y `D0` (año, mes empezando en 0 y día de inicio).
- **Juegos del día:** la lista `R`. Hay de tipo adivinanza, emojis, secuencia, trivia, ordenar letras (con 3 pistas), memoria, reflejos y rasca y gana.
- **Premio:** el texto "Tatuaje de besties" dentro de la función `scratch`.
- **Aviso del 21 de diciembre:** la fecha `tgt` y el texto de la función `upd`.
- **Gatos:** el número de stickers (`n<20`) y la lista de emojis `E`.

## ℹ️ Cosas a tener en cuenta
- Los días se desbloquean según la fecha del dispositivo de quien abre la web.
- El progreso y las pistas usadas se guardan en el navegador (localStorage), así que no se comparten entre dispositivos.
- Truco de prueba: toca el título 5 veces para desbloquear todos los días.
- Si cambias los juegos o las fechas, cambia también la constante `K` (por ejemplo a `mini-v4`) para reiniciar el progreso guardado.
