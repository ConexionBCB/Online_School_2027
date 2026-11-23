---
layout: page
title: Programa
permalink: /schedule/
---

<p class="day-logo">
  <img src="{{ site.baseurl }}/assets/img/logos/logo_auxiliar.svg" alt="Conexión BCB" class="page-logo-small" />
</p>

{%- assign c = site.curso -%}

Siete sesiones, {{ c.horario_corto }}, {{ c.fechas_largo }}.
Todas las sesiones son **{{ c.modalidad }}** y los horarios están en
**{{ c.zona_horaria }}**.

<!-- El calendario se genera desde _data/sesiones.yml. Para cambiar una fecha,
     un ponente o un tema, edita ese fichero: esta tabla se actualiza sola. -->

<table class="schedule-table">
  <thead>
    <tr>
      <th>Sesión</th>
      <th>Fecha</th>
      <th>Tema</th>
      <th>Ponente</th>
    </tr>
  </thead>
  <tbody>
    {% for s in site.data.sesiones %}
    <tr>
      <td><a href="{{ site.baseurl }}/sesion{{ s.num }}/">S{{ s.num }}</a></td>
      <td>{{ s.fecha }}</td>
      <td><a href="{{ site.baseurl }}/sesion{{ s.num }}/">{{ s.tema }}</a></td>
      <td>{{ s.ponente }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

> No hay sesiones el 23 ni el 25 de marzo: es Semana Santa (Domingo de Pascua,
> 28 de marzo de 2027).

## Horario de cada sesión

Las siete sesiones siguen la misma estructura:

| Hora        | Contenido          |
|-------------|--------------------|
| 15:00–16:30 | Teoría             |
| 16:30–16:45 | Pausa              |
| 16:45–18:15 | Práctica guiada    |
| 18:15–18:30 | Dudas y cierre     |
{: .schedule-table }

El reparto interno entre teoría y práctica lo ajusta cada ponente; la hora de
inicio y de fin son fijas.

## Actividad para reconocimiento de ECTS

A lo largo del curso, cada participante podrá preparar un **syllabus breve**
sobre uno de los temas tratados. Esta actividad es necesaria para la
**obtención de créditos ECTS**. Los criterios de evaluación y la plantilla se
explican en la primera sesión, y la entrega se realiza en
[Classroom]({{ site.baseurl }}/classroom/).

## Dónde está todo

Las clases en directo y todo el material se encuentran en
[Classroom]({{ site.baseurl }}/classroom/). Para información sobre requisitos
técnicos, matrícula y contacto, consulta la página de
[Logística]({{ site.baseurl }}/logistics/).
