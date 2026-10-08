# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Qué es este repo

Guías visuales e interactivas en español para personas que empiezan con herramientas de IA. Quien lo usa está empezando: explica los pasos en lenguaje sencillo y responde en español.

No hay build, dependencias ni tests. Cada guía es un único archivo HTML autocontenido (CSS y JS en línea; solo las tipografías vienen de Google Fonts). Para probar una guía, ábrela en el navegador.

Remoto: `https://github.com/msarmengolAsepeyo/guias-ia` (privado, rama `main`).

## Guías y sus Artifacts publicados

Cada guía también está publicada como Artifact de claude.ai. Al cambiar una guía, actualiza el archivo local **y** republica en la misma URL para que el enlace siga funcionando:

| Archivo | Artifact |
|---|---|
| `primeros-pasos.html` | https://claude.ai/artifact/C8DqjDi5ebzq21xxhSVxmF |
| `perplexity-max.html` | https://claude.ai/artifact/7baEBeoyrYrjvk3DTvt3uN |

Los archivos locales llevan un envoltorio (`<!doctype html>…<head>` con charset y viewport, `<body>` y los cierres) para abrirse bien con doble clic. El Artifact espera el contenido **sin** ese envoltorio, porque la publicación añade el suyo. Para republicar: lee primero el Artifact (`action: "read"` con su URL), aplica los cambios, quita las líneas del envoltorio en una copia y publica esa copia con `url`. Después actualiza el archivo local con el envoltorio.

## Convenciones de las guías

- Todos los colores son tokens CSS en `:root`, redefinidos para modo oscuro en `@media (prefers-color-scheme: dark)` (con `:root:not([data-theme="light"])`) y en `:root[data-theme="dark"]`. No uses colores literales en los componentes.
- Cada guía tiene su propia identidad visual (tipografías y paleta distintas). No copies el estilo de una a otra.
- Las listas de progreso guardan su estado en `localStorage` como un array de booleanos indexado por posición (`primeros-pasos-checks`, `pplx-max-checks`). Añade los puntos nuevos **al final** para no desordenar el progreso guardado. Envuelve cada acceso a `localStorage` en `try/catch`.
- Los botones de copiar usan `navigator.clipboard.writeText` y, si falla, seleccionan el texto para copiarlo con Ctrl+C.

## Datos de Perplexity Max

`perplexity-max.html` es una guía no oficial con datos del 8 de octubre de 2026. Las cifras de créditos (100 créditos = 1 $, 10.000 al mes en Max, bonus de 35.000, rangos por tamaño de tarea, tope de 200 $ ampliable a 5.000 $) vienen del artículo del centro de ayuda «How Credits Work on Perplexity» (actualizado el 24 de junio de 2026). Lo de Model Council dentro de Computer viene de fuentes externas. La página marca como «No documentado» lo que no se ha podido confirmar. Mantén esa distinción al actualizarla y cambia la fecha del pie.

La red de este equipo bloquea `perplexity.ai` por un error de certificado (`SEC_E_UNTRUSTED_ROOT`). No desactives la verificación TLS: usa las copias del centro de ayuda en `intercom.help/perplexity-ai/...` o fuentes externas.
