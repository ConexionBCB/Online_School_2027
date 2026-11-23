---
layout: page
title: Classroom
permalink: /classroom/
---

<p class="day-logo">
  <img src="{{ site.baseurl }}/assets/img/logos/logo_auxiliar.svg" alt="Conexión BCB" class="page-logo-small" />
</p>

{%- assign c = site.curso -%}

El curso se imparte a través de **Google Classroom** y **Google Meet**. Al ser
una edición {{ c.modalidad }}, Classroom no es un complemento: es el aula. Desde
ahí se entra a las clases en directo, se descarga el material y se entregan las
actividades.

{% if c.classroom_url and c.classroom_url != '' %}
<p>
  <a href="{{ c.classroom_url }}" class="btn btn-primary" target="_blank" rel="noopener noreferrer">
    Entrar en Classroom
  </a>
</p>
{% else %}
<p class="notice notice--pending">
  La clase se abrirá antes del comienzo del curso. Las personas admitidas
  recibirán una invitación por correo electrónico; no hace falta hacer nada
  hasta entonces.
</p>
{% endif %}

## Cómo se accede
{: #como-se-accede }

No hay usuario ni contraseña del curso. El acceso va asociado a **tu cuenta de
Google**:

1. Al ser admitida tu solicitud, recibirás una **invitación por correo** a la
   dirección que indiques en la preinscripción.
2. Aceptas la invitación y entras en la clase con tu cuenta de Google.
3. A partir de ahí, la clase aparece en [classroom.google.com](https://classroom.google.com/)
   cada vez que inicies sesión.

> **Importante:** en la preinscripción se te pedirá la dirección de la **cuenta
> de Google** que vas a usar en el curso. Puede ser un Gmail o la cuenta de tu
> institución si esta usa Google Workspace. Si tu correo de trabajo no es una
> cuenta de Google, indica una que sí lo sea, o crea una cuenta de Google
> gratuita con tu dirección habitual. La invitación solo funciona en una cuenta
> de Google, así que una dirección equivocada aquí es el motivo más frecuente de
> no poder entrar el primer día.

El código de la clase **no se publica en esta web**, y por una razón concreta:
las plazas son limitadas y las sesiones son para quien está inscrito.

## Las clases en directo

Cada sesión tiene su propio apartado en Classroom, con el enlace de **Google
Meet** de la clase. Siempre es el mismo enlace, y se entra desde Classroom.

- **Entrada:** desde el apartado de la sesión, unos minutos antes de las {{ c.hora_inicio }}.
- **La sala se abre cuando entra el profesorado.** Si llegas antes, esperarás en
  la sala de espera: es normal, no es un error.
- **Preguntas:** en voz, levantando la mano, o por el chat. Cada sesión tiene
  además un espacio de dudas para después de la clase.
- **Prácticas:** se trabaja mientras el ponente guía. Las dudas concretas se
  atienden sin detener al grupo.
- **Pausa:** de 16:30 a 16:45.

{% if c.grabaciones == 'sí' %}
Las sesiones **se graban** y la grabación queda disponible en Classroom para las
personas inscritas. Al preinscribirte se te pedirá consentimiento explícito; si
prefieres no aparecer, basta con mantener la cámara apagada y usar el chat.
{% elsif c.grabaciones == 'no' %}
Las sesiones **no se graban**. El material queda disponible en Classroom, pero
las clases hay que seguirlas en directo.
{% endif %}

> **Antes de la primera sesión** se abrirá una **prueba técnica** en Classroom
> para comprobar cámara, micrófono y acceso. Son cinco minutos que evitan
> empezar el 9 de marzo con un problema de audio.

## Qué encontrarás

Un apartado por sesión, cada uno con:

- **Enlace a la clase en directo** por Google Meet.
- **Diapositivas y material teórico.**
- **Cuadernos de prácticas** (Jupyter, R Markdown, Quarto) y scripts.
- **Datos de ejemplo**, o instrucciones para acceder a ellos.
- **Espacio de dudas** de la sesión.
- **Tareas**, cuando la sesión tenga actividad evaluable.

Y un apartado general con la guía de bienvenida, los horarios con zona horaria,
la prueba técnica, el contacto para incidencias, la **entrega del mini‑syllabus**
para el reconocimiento de créditos ECTS y la encuesta final.

## Requisitos técnicos

Navegador actualizado, **auriculares con micrófono** y, si es posible, **dos
pantallas** (una para la clase y otra para practicar). Los detalles están en
[Logística]({{ site.baseurl }}/logistics/#requisitos-tecnicos).

## Problemas de acceso

Escribe a [{{ c.email }}](mailto:{{ c.email }}) indicando la dirección con la que
te preinscribiste. Durante las sesiones habrá una persona de la organización
disponible para incidencias técnicas.

## Para el profesorado

Cada ponente entra en la clase como **profesor**, lo que permite subir y
organizar el material de su sesión y moderar su propia clase en Meet, sin
depender de la organización. Los detalles están en la
[guía del profesorado]({{ c.repo_url }}/blob/main/CONTRIBUTING.md).

## Material de acceso abierto

El material de acceso abierto se publica también en este repositorio, en las
carpetas `materials/sesionN/`, de modo que siga disponible cuando la clase se
cierre al terminar la edición. El material con restricciones de licencia y los
datos de gran tamaño permanecen únicamente en Classroom.
