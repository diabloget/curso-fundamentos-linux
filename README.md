# Fundamentos de Linux - Clase 3

Presentación en Slidev. Mantiene el diseño de las clases 1 y 2.

## Preparación

1. Conserva o copia la carpeta `public` de tu repositorio. En particular, deben existir `public/img/RocketGirlsLogo.png` y `public/fonts/Jersey10-Regular.ttf`.
2. Instala dependencias en esta carpeta con `deno install`.
3. Ejecuta `deno task check:assets` para comprobar el logo y la fuente.
4. Inicia la presentación con `deno task dev` y abre http://localhost:3030/.

Se usa Slidev 53.1.0 para evitar el error de importación de imágenes de la versión 52.16.0. No agregues `/public` en las rutas del HTML. Si en tu repositorio usas otra versión reciente y funcional de Slidev, puedes conservarla.

Para exportar a PDF: `deno task export` (modo oscuro). La exportación necesita Chromium para Playwright; si Deno te avisa sobre scripts ignorados, instala el navegador siguiendo la documentación de Playwright/Slidev. No uses Ctrl+P para imprimir las diapositivas.

## Archivos

- `slides.md`: contenido original con correcciones puntuales.
- `style.css`: estilo unificado con la Clase 1 y la Clase 2.
- `CAMBIOS.md`: registro de diferencias.
- `scripts/check-assets.mjs`: comprobación de recursos locales.

Las imágenes, iconos y fuentes de la carpeta `public` no están incluidos porque los archivos de imágenes y fuentes no venían adjuntos.
