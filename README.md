# Escuela Online en Bioinformática Avanzada 2027

Sitio web y materiales de la Escuela Online organizada por la Conexión de
Biología Computacional y Bioinformática del CSIC.

**Edición 100 % en línea**, con un máximo de 30 participantes. Siete sesiones,
martes y jueves de 15:00 a 18:30 (CET), del 9 de marzo al 6 de abril de 2027.
Las clases se imparten por **Google Meet** y se entra desde **Google Classroom**.

Sitio publicado (provisional): https://iandreu.github.io/Online_School_2027/

> **El repositorio está alojado temporalmente en la cuenta `IAndreu`.** El
> destino final es la organización `ConexionBCB`, a la espera de permisos.
> Cuando se transfiera, hay que cambiar **cuatro líneas** (ver más abajo:
> «Después de transferir a ConexionBCB»); el nombre del repositorio no cambia,
> así que `baseurl` se queda como está.

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

Y abrir http://localhost:4000/Online_School_2027/

## Publicación

GitHub Pages construye el sitio automáticamente al hacer push a `main`. En
**Settings › Pages**, seleccionar *Deploy from a branch* → `main` → `/ (root)`.

Si el repositorio se renombra, hay que actualizar `baseurl` en `_config.yml` para
que coincida, o los enlaces y los estilos se romperán.

### Usar un dominio propio (p. ej. `escuela-bcb.org`)

Si se compra un dominio para la cuenta de Google del curso, **el mismo dominio
puede servir esta web**, que pasaría de
`conexionbcb.github.io/Online_School_2027/` a `escuela-bcb.org`. GitHub Pages
admite dominios propios con HTTPS sin coste. Pasos:

1. **En el repositorio:** crear un fichero `CNAME` en la raíz cuyo único
   contenido sea el dominio, sin `https://` ni barra final:

   ```
   escuela-bcb.org
   ```

2. **En el DNS del dominio**, añadir los registros que indica GitHub en
   *Settings › Pages › Custom domain*. Para un dominio raíz son cuatro
   registros `A` a las IP de GitHub Pages (y/o `AAAA` para IPv6); para un
   subdominio tipo `escuela.cragenomica.es`, un único `CNAME` a
   `conexionbcb.github.io`. **Copiar los valores de la propia página de GitHub**,
   que es la fuente al día.

3. **En `_config.yml`**, cambiar las dos claves:

   ```yaml
   baseurl: ""                       # el sitio pasa a estar en la raíz
   url: "https://escuela-bcb.org"
   ```

   Este paso es imprescindible: con `baseurl` apuntando a
   `/Online_School_2027`, todos los enlaces y los estilos quedarían rotos en el
   dominio nuevo.

4. En *Settings › Pages*, marcar **Enforce HTTPS** cuando GitHub haya emitido el
   certificado (tarda unos minutos).

> El dominio de GitHub (`conexionbcb.github.io`) **no** sirve para verificar una
> cuenta de Google Workspace: es un subdominio de GitHub, no vuestro, y no se
> pueden añadir registros DNS en él.

## Después de transferir a ConexionBCB

El nombre del repositorio (`Online_School_2027`) no cambia con la transferencia,
así que **`baseurl` se queda como está**. Solo hay que sustituir `IAndreu` por
`ConexionBCB` en estos cuatro sitios:

| Fichero | Línea |
|---|---|
| `_config.yml` | `url: "https://iandreu.github.io"` → `https://conexionbcb.github.io` |
| `_config.yml` | `curso.repo_url` |
| `CONTRIBUTING.md` | el enlace al programa |
| `CONTRIBUTING.md` | el `git clone` del apartado de subir material |

Para localizarlas:

```bash
grep -rni "iandreu" --exclude-dir=.git .
```

Y actualizar el remoto local:

```bash
git remote set-url origin https://github.com/ConexionBCB/Online_School_2027.git
```

Ojo: GitHub redirige los repositorios transferidos, pero **no** las páginas
publicadas de una cuenta a otra. La dirección de la web cambiará de
`iandreu.github.io/Online_School_2027/` a
`conexionbcb.github.io/Online_School_2027/`.

## Licencia

<!-- TODO (organización): elegir licencia. Sugerencia: CC BY 4.0 para los
     contenidos y MIT para el código del sitio. -->
Pendiente de definir.
