---
title: "Registro inicial"
date: 2026-06-08
description: "La primera senal del blog: una prueba viva del flujo con Markdown y Jekyll."
tags: [blog, jekyll, markdown]
---

Este blog esta construido para funcionar con archivos Markdown simples.

Cada entrada vive en `_posts/` y usa **YAML front matter** al inicio del archivo.
Esa metadata define el titulo, la fecha, la descripcion y las etiquetas que aparecen
en la interfaz.

## Formato basico

```md
---
title: "Titulo de la entrada"
date: 2026-06-08
description: "Resumen corto de la entrada."
tags: [linux, terminal, notas]
---

Contenido de la entrada en Markdown.
```

## Convencion de nombres

Los posts deben guardarse asi:

```text
_posts/YYYY-MM-DD-titulo-en-minusculas.md
```

Ejemplo:

```text
_posts/2026-06-08-registro-inicial.md
```

Con eso basta: GitHub Pages ejecuta Jekyll y publica la entrada automaticamente.
