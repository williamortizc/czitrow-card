# Blog

Este sitio usa Jekyll nativo de GitHub Pages para publicar entradas desde Markdown.

## Arquitectura

- `index.html`: home principal. No depende de layouts Jekyll para evitar cambios visuales no deseados.
- `blog/index.html`: indice del blog. Usa Liquid para listar automaticamente `site.posts`.
- `_posts/`: entradas publicas del blog. Todo archivo valido aqui se publica.
- `_drafts/`: borradores o respaldos. GitHub Pages no los publica por defecto.
- `_layouts/default.html`: base HTML para paginas Jekyll del blog.
- `_layouts/post.html`: plantilla visual para cada entrada.
- `_includes/matrix-background.html`: fondo animado compartido por blog y posts.
- `styles.css`: estilos del home, blog y entradas.

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

## Crear un borrador

Guarda el archivo en `_drafts/`:

```text
_drafts/mi-borrador.md
```

Los borradores conservan el mismo formato de front matter, pero no aparecen en el sitio publico.

## Publicar un borrador

Mueve el archivo de `_drafts/` a `_posts/` y renombralo con fecha:

```text
_posts/2026-06-08-mi-borrador.md
```

## Rutas

- Blog: `/blog/`
- Entradas: `/blog/YYYY/MM/DD/titulo/`

## Ideas para primeras entradas

- Como esta construido este sitio: GitHub Pages, Jekyll y una UI cyberpunk sin framework.
- Mi flujo minimo para publicar notas tecnicas con Markdown.
- Comandos esenciales para diagnosticar una maquina Linux.
- Como organizar una bitacora tecnica personal sin perder velocidad.
- Checklist personal antes de exponer un servicio en internet.
