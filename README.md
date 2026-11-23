# Escuela de Invierno en Bioinformática Avanzada 2027

Sitio web y materiales de la Escuela de Invierno organizada por la Conexión de
Biología Computacional y Bioinformática del CSIC.

**Edición 100 % en línea**, con un máximo de 30 participantes. Siete sesiones,
martes y jueves de 15:00 a 18:30 (CET), del 9 de marzo al 6 de abril de 2027.
Las clases se imparten por **Google Meet** y se entra desde **Google Classroom**.

Sitio publicado: https://conexionbcb.github.io/Winter_School_2027/

Este repositorio parte de la [Escuela de Verano 2026](https://github.com/ConexionBCB/Summer_School_2026).

---

## Los dos ficheros que hay que editar

Casi todo lo que cambia entre ediciones está en dos sitios, y en ningún otro:

| Fichero | Qué contiene |
|---|---|
| **`_config.yml`** → bloque `curso:` | Precio, plazos, enlaces a Classroom y al formulario, zona horaria, contacto |
| **`_data/sesiones.yml`** | **El calendario**: fecha, ponente y tema de las siete sesiones |

El calendario es la única fuente para la portada, el programa, las páginas de
cada sesión y la navegación entre ellas. Si cambia una fecha, se cambia ahí y el
sitio entero se actualiza.

Lo que queda pendiente está marcado con `[TBC]`:

```bash
grep -rn "TBC" --exclude-dir=.git .          # lo que falta por rellenar
grep -rn "TODO (organización)" --exclude-dir=.git .
```

## Estructura

| Ruta | Qué es |
|---|---|
| `_config.yml` | Datos del curso y navegación |
| `_data/sesiones.yml` | Calendario de las siete sesiones |
| `_data/profesorado.yml` | Profesorado (página de Organización) |
| `_data/organizadores.yml` | Equipo organizador |
| `_data/patrocinadores.yml` | Entidades patrocinadoras |
| `index.md` | Página de inicio |
| `pages/sesion1.md` … `sesion7.md` | Una página por sesión (cortas: los datos vienen del calendario) |
| `pages/schedule.md` | Programa |
| `pages/classroom.md` | Cómo se accede a Classroom y Meet |
| `pages/organizacion.md`, `pages/logistics.md` | Organización y logística |
| `materials/sesionN/` | Material de cada sesión, una subcarpeta por ponente |
| `materials/_plantilla-ponente/` | Plantilla de README para cada ponente |
| `_layouts/sesion.html` | Plantilla común de las siete sesiones |
| `assets/css/style.css` | Estilos |
| `CONTRIBUTING.md` | **Guía para el profesorado: cómo subir material y dar la sesión** |

## Google Classroom y Google Meet

El sitio web es estático: **enlaza** a Classroom, no lo contiene. La página
`/classroom/` y los botones leen `curso.classroom_url` de `_config.yml`.
Mientras esté vacío se muestra un aviso de "próximamente" en lugar de un enlace
roto; en cuanto se rellene, aparecen los botones. No hay que editar ninguna
página.

Los enlaces de las sesiones y el código de la clase **no se publican en esta
web**: el acceso es por invitación a la cuenta de Google que cada persona indica
al preinscribirse.

## Añadir una sesión o cambiar un ponente

1. Edita la entrada en `_data/sesiones.yml`.
2. Si es una sesión nueva, crea `pages/sesionN.md` copiando otra (solo cambian
   `title`, `permalink` y `sesion:`) y la carpeta `materials/sesionN/`.
3. Si cambia el profesorado, actualiza también `_data/profesorado.yml`.

## Ver el sitio en local

```bash
bundle install
bundle exec jekyll serve
```

Y abrir http://localhost:4000/Winter_School_2027/

## Publicación

GitHub Pages construye el sitio automáticamente al hacer push a `main`. En
**Settings › Pages**, seleccionar *Deploy from a branch* → `main` → `/ (root)`.

Si el repositorio se renombra, hay que actualizar `baseurl` en `_config.yml` para
que coincida, o los enlaces y los estilos se romperán.

## Licencia

<!-- TODO (organización): elegir licencia. Sugerencia: CC BY 4.0 para los
     contenidos y MIT para el código del sitio. -->
Pendiente de definir.
