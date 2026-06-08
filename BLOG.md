# Blog

Este sitio usa Jekyll nativo de GitHub Pages para publicar entradas desde Markdown.

## Crear una entrada

1. Crea un archivo en `_posts/` con este formato:

```text
YYYY-MM-DD-titulo-de-la-entrada.md
```

Ejemplo:

```text
_posts/2026-06-08-mi-entrada.md
```

2. Agrega YAML front matter al inicio:

```md
---
title: "Mi entrada"
date: 2026-06-08
description: "Resumen corto para la lista del blog."
tags: [linux, terminal, notas]
---

Contenido en Markdown.
```

3. Publica:

```bash
git add .
git commit -m "post: add mi entrada"
git push origin main
```

GitHub Pages construye el blog automaticamente.

## Rutas

- Blog: `/blog/`
- Entradas: `/blog/YYYY/MM/DD/titulo/`
