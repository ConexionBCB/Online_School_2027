---
layout: page
title: Logística
permalink: /logistics/
---

<p class="day-logo">
  <img src="{{ site.baseurl }}/assets/img/logos/logo_auxiliar.svg" alt="Conexión BCB" class="page-logo-small" />
</p>

{%- assign c = site.curso -%}

Información práctica de la {{ site.title }}.

<!-- TODO (organización): los valores marcados como [TBC] se editan en
     `_config.yml`, bloque `curso:`. El calendario está en
     `_data/sesiones.yml`. No hace falta tocar esta página. -->

## Formato

Esta edición es **{{ c.modalidad }}**, a través de **Google Classroom** y
**Google Meet**. Todas las sesiones, teóricas y prácticas, se imparten en
directo. No hay desplazamiento, ni sede física, ni alojamiento.

**Plazas limitadas a {{ c.plazas }} participantes.** El curso incluye sesiones
prácticas guiadas: el límite existe para que el profesorado pueda atender a cada
persona durante los ejercicios.

## Fechas y horario

- **{{ c.fechas_largo }}.**
- Sesiones: **{{ c.horario_corto }}**, con una pausa de 16:30 a 16:45.
- El calendario completo, con el tema y el ponente de cada sesión, está en la
  página de [Programa]({{ site.baseurl }}/schedule/).

> **Todos los horarios están en {{ c.zona_horaria }}.** Si participas desde otro
> huso horario, comprueba la diferencia antes de la primera sesión.

> No hay sesiones el 23 ni el 25 de marzo: es Semana Santa.

## Matrícula

- **Precio:** {{ c.precio }} por persona.
{% if c.descuento_socios != '[TBC]' and c.descuento_socios != '' %}- **Descuento socios SEBiBC:** {{ c.descuento_socios }} de descuento para personas socias de la
  [Sociedad Española de Bioinformática y Biología Computacional (SEBiBC)](https://www.sebibc.es/)
  (precio final {{ c.precio_socios }}).
{% endif %}- La matrícula incluye:
  - Acceso a las siete sesiones en directo.
  - Acceso a [Classroom]({{ site.baseurl }}/classroom/) con todo el material docente.
  - Acceso al entorno donde se realizan las sesiones prácticas.
  - Certificado de asistencia.

## Preinscripción

{% if c.preinscripcion_url and c.preinscripcion_url != '' %}
La preinscripción se realiza mediante un formulario en línea alojado en los
servicios del CSIC{% if c.preinscripcion_cierre != '[TBC]' and c.preinscripcion_cierre != '' %} y está abierta
hasta el **{{ c.preinscripcion_cierre }}**{% endif %}.

<p style="margin-top: var(--space-lg);">
  <a href="{{ c.preinscripcion_url }}" class="btn btn-secondary btn-preinscripcion" target="_blank" rel="noopener noreferrer">Formulario de preinscripción</a>
</p>
{% else %}
El formulario de preinscripción se publicará próximamente en esta página,
junto con las fechas del plazo.
{% endif %}

En el formulario se te pedirá la dirección de la **cuenta de Google personal**
que usarás en el curso: es la que recibirá la invitación a Classroom. Conviene
leer la [página de Classroom]({{ site.baseurl }}/classroom/#como-se-accede)
antes de rellenarlo, porque la cuenta institucional puede no servir.

## Requisitos técnicos
{: #requisitos-tecnicos }

Lo que necesitas para seguir el curso:

| | Mínimo | Recomendado |
|---|---|---|
| Cuenta | **Una cuenta de Google** (obligatorio para Classroom y Meet) | **Una cuenta personal de Gmail** (ver nota abajo) |
| Conexión | 5 Mbps de bajada / 2 de subida | 20 Mbps, por cable antes que por wifi |
| Navegador | Chrome, Firefox, Edge o Safari actualizados | Chrome o Firefox al día |
| Audio | Auriculares con micrófono | Auriculares con micrófono (evitan el eco) |
| Cámara | Recomendada | Recomendada |
| Pantalla | 1 monitor | **2 monitores o 2 dispositivos**: uno para la clase y otro para practicar |

Tres puntos que marcan la diferencia:

- **Necesitas una cuenta de Google, y conviene que sea personal.** Classroom y
  Meet no funcionan sin ella. Usa preferentemente **un Gmail personal**: Google
  Classroom restringe qué tipos de cuenta pueden unirse a qué clases, y una
  cuenta corporativa o universitaria gestionada con Google puede quedar
  bloqueada. No hace falta que sea `@gmail.com` —se puede crear una cuenta de
  Google personal con cualquier dirección—, pero si tu institución ya gestiona
  su correo con Google, esa dirección no sirve para esto. Más detalle en la
  [página de Classroom]({{ site.baseurl }}/classroom/#como-se-accede).
- **Usa auriculares.** El altavoz del portátil provoca eco y obliga a silenciar
  a todo el mundo, lo que mata las preguntas.
- **Dos pantallas, o un segundo dispositivo.** Las sesiones prácticas consisten
  en seguir al ponente mientras escribes tus propios comandos. Una tablet o un
  segundo portátil para la videollamada sirve perfectamente.

**Prueba de conexión:** antes de la primera sesión se abrirá una prueba técnica
en Classroom para comprobar cámara, micrófono y acceso. Dedícale cinco minutos.

## Requisitos previos

- Familiaridad con la línea de comandos (Unix/Linux) y con conceptos de
  bioinformática (R, Python, análisis de RNA‑Seq, llamado de variantes, etc.).
- El curso está orientado a personas que ya trabajan o estudian en bioinformática
  y quieren profundizar en temas avanzados. Resulta especialmente útil para
  quienes preparan o imparten docencia en estas áreas.

## Certificado

Las personas que sigan el curso reciben un **certificado de asistencia**, que se
emite después de la última sesión.

## Contacto

- **Correo de contacto:** [{{ c.email }}](mailto:{{ c.email }})
