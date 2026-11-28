# MálagaGram

Galería visual de pueblos y lugares de la provincia de Málaga hecha con HTML5 y CSS3. El proyecto es una práctica de maquetación adaptable: una columna en móvil, dos columnas en tableta y una rejilla con menú lateral en escritorio. No lleva JavaScript.

## Enlaces

- Repositorio: https://github.com/Cristianhr99/malagagram
- Web publicada: https://cristianhr99.github.io/malagagram/
- PDF con los enlaces: `Enlaces.pdf`

## Estructura

- `index.html`: página principal con etiquetas semánticas y metadatos.
- `styles.css`: estilos mobile-first, media queries de tableta, escritorio e impresión.
- `assets/raw`: fotografías originales descargadas de Wikimedia Commons.
- `assets/img`: versiones de 400 px y 1000 px que usa la web.
- `.vscode/tasks.json`: tarea para generar las imágenes desde VS Code.

## Ver la web

Se puede abrir `index.html` directamente en el navegador. Si se quiere servir con un servidor local, desde la carpeta del proyecto:

```
python -m http.server 8000
```

Después se entra en `http://localhost:8000`.

## Generar las imágenes

Hay que tener ImageMagick instalado y `magick` disponible en el PATH. En VS Code se ejecuta la tarea **Generar imágenes optimizadas** (`Ctrl+Shift+P` → *Tasks: Run Task*). La tarea recorre `assets/raw` y crea en `assets/img` dos archivos por foto:

- `nombre-mobile.jpg`, con ancho de 400 px.
- `nombre-desktop.jpg`, con ancho de 1000 px.

También se puede hacer a mano con ImageMagick:

```
magick assets/raw/ronda.jpg -resize 400x -strip -quality 82 assets/img/ronda-mobile.jpg
magick assets/raw/ronda.jpg -resize 1000x -strip -quality 85 assets/img/ronda-desktop.jpg
```

## Publicación

Para GitHub Pages: subir la carpeta a un repositorio, ir a *Settings → Pages*, elegir la rama principal y la carpeta `/ (root)`. La web queda en `https://<usuario>.github.io/<repositorio>/`. Al publicar, conviene cambiar `og:image` por la URL absoluta de una de las imágenes.

## Créditos de las fotos

Todas vienen de Wikimedia Commons y se han reducido de tamaño con ImageMagick.

- Alcazaba de Málaga: Diego Delso, CC BY-SA 4.0.
- Puente Nuevo de Ronda: Wolfgang Moroder, CC BY-SA 3.0.
- Balcón de Europa (Nerja): Tuxyso, CC BY-SA 3.0.
- Casco antiguo de Marbella: Ypsilon from Finland, CC0.
- Alcazaba de Antequera: Jebulon, CC0.
- Frigiliana: Jorge Saturno, CC BY 4.0.
- Caminito del Rey: Diego Delso, CC BY-SA 4.0.
- Playa de la Carihuela (Torremolinos): Biblioteca de la Facultad de Empresa y Gestión Pública de la Universidad de Zaragoza, CC BY-SA 2.0.
