# blog-assets

Repositorio de assets públicos para artículos.

Este directorio entra al repositorio principal como `git subtree` y debe poder publicarse de forma independiente para que DEV.to, WordPress.com y otras plataformas resuelvan imágenes por URL pública.

## Estructura

Usa carpetas semánticas y estables:

```text
assets/
  articles/
    2026/
      ia-no-solo-big-tech/
        cover.png
        arquitectura.svg
  shared/
    logos/
    diagrams/
    screenshots/
```

Convenciones:

- `articles/<year>/<slug>/`: assets propios de un artículo.
- `shared/`: assets reutilizables entre artículos.
- `cover.*`: imagen principal del artículo.
- Nombres en minúsculas, sin espacios, separados por `-`.
- Preferir `png`, `jpg`, `webp` o `svg` optimizado.

## Uso en Markdown

En artículos, referencia assets desde la raíz del repo:

```markdown
![Arquitectura](/assets/articles/2026/ia-no-solo-big-tech/arquitectura.svg)
```

O sin slash inicial:

```markdown
![Arquitectura](assets/articles/2026/ia-no-solo-big-tech/arquitectura.svg)
```

El publisher transforma esas rutas a URLs públicas antes de enviar a plataformas.

## URL pública

Por defecto el publisher usa:

```text
https://rafex.github.io/blog-assets
```

Así:

```text
/assets/articles/2026/ia-no-solo-big-tech/cover.png
```

se convierte en:

```text
https://rafex.github.io/blog-assets/articles/2026/ia-no-solo-big-tech/cover.png
```

Puedes sobrescribir la base con:

```bash
ASSETS_PUBLIC_BASE_URL=https://cdn.example.com/blog-assets
```
