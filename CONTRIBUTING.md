# Guía para el profesorado

Esta guía explica **dónde va cada cosa**, **cómo subir tu material** y **cómo dar
tu sesión en línea** en la Escuela Online en Bioinformática Avanzada 2027.

> **Esta edición es 100 % en línea**, a través de **Google Classroom** y **Google
> Meet**, con un grupo de **30 participantes como máximo**. Cada sesión es de
> **15:00 a 18:30 (CET)**, y la imparte una sola persona. El apartado 4 recoge lo
> que conviene preparar de forma distinta a una clase presencial; si solo vas a
> leer una sección, que sea esa.

Tu sesión y tu fecha están en el [programa](https://iandreu.github.io/Online_School_2027/schedule/).

## Dónde va cada cosa

| Lo que quieres publicar | Dónde va | Por qué |
|---|---|---|
| Diapositivas, guiones de prácticas, cuadernos, scripts de acceso abierto | **Classroom** y, si son abiertos, **este repositorio** | Classroom para el grupo; el repositorio para que siga disponible después |
| Datos de ejemplo grandes (> 50 MB) | **Classroom / Drive**, o Zenodo | GitHub rechaza ficheros grandes |
| Material con licencia restrictiva o de terceros | **Solo Classroom** | Acceso limitado a personas inscritas |
| Ejercicios, dudas, comentarios | **Classroom** | Necesita identificación y seguimiento |
| Datos personales o sensibles | **Classroom**, nunca en el repositorio | Un repositorio público no es el sitio |

La regla breve: **Classroom es el aula; el repositorio es el archivo.** Lo que
quieras que siga existiendo dentro de dos años, súbelo también aquí.

---

## 1. Tu apartado en Google Classroom

Entras en la clase como **profesor**, lo que te permite subir y reordenar el
material de tu sesión, y **moderar tu propia clase en Meet**, sin depender de la
organización.

1. Acepta la invitación que recibirás por correo y entra en la clase.
2. Busca el apartado de tu sesión: **Sesión N — tu tema**. Dentro encontrarás ya
   creado el enlace de **Meet**: es por donde entrarás a dar la clase y por donde
   entra el grupo. No tienes que crear ninguna reunión ni generar ningún enlace.
3. En **Trabajo de clase**, usa **Crear** para añadir:
   - **Material** — diapositivas, PDF, cuadernos, enlaces. Es lo que usarás casi
     siempre.
   - **Tarea** — si quieres proponer un ejercicio con fecha límite. No hay
     evaluación obligatoria en el curso: úsala solo si te resulta útil.
   - **Pregunta** — para una consulta rápida al grupo.
4. Asigna cada elemento al **tema** de tu sesión, para que no aparezca suelto.
5. Puedes **programar** la publicación: así dejas el material preparado con
   antelación y se publica el día que te interese.

**Plazo:** deja visible el material teórico **al menos una semana antes** de tu
sesión. En línea esto importa más que en persona: mucha gente sigue la clase con
las diapositivas abiertas en una segunda pantalla.

**Atajo útil:** puedes arrastrar ficheros directamente desde tu escritorio al
crear un *Material*; Classroom los sube a la carpeta de Drive de la clase.

---

## 2. Tu carpeta en el repositorio

El material de acceso abierto va además aquí, en la carpeta de tu sesión:

```
materials/
  sesion1/          Aureliano Bombarely — Ensamblado de genomas
  sesion2/          Juan Fernández-Recio — AlphaFold
  sesion3/          Javier De Las Rivas — Célula única
  sesion4/          Daniel Jesús García García — Transcriptómica espacial
  sesion5/          Ana Conesa — Lecturas largas
  sesion6/          Arnau Montagud — Biología de sistemas
  sesion7/          Ian Morilla — Multi-ómica
      apellido-tema/        <- tu carpeta
        README.md           <- describe la sesión (plantilla incluida)
        slides/
        practicas/
        datos/
```

Nómbrala en minúsculas, con guiones y sin acentos: `bombarely-ensamblado`,
`conesa-long-reads`. Dentro mandas tú; mantén solo el `README.md` en la raíz.

Hay una plantilla en [`materials/_plantilla-ponente/README.md`](materials/_plantilla-ponente/README.md).
Cópiala a tu carpeta y rellénala: de qué va la sesión, qué software hace falta,
en qué orden se usan los ficheros, los puntos de control de la práctica y la
licencia de tu material.

### Cómo subirlo

**Opción A — desde la web de GitHub (sin usar git).** La vía más rápida:

1. Abre la carpeta de tu sesión, p. ej. `materials/sesion2/`.
2. **Add file › Upload files**, y arrastra tus ficheros.
3. Para crear tu carpeta, en **Add file › Create new file** escribe
   `apellido-tema/README.md` — la barra crea la carpeta automáticamente.
4. Escribe una descripción breve y pulsa **Commit changes**.

Si no tienes permiso de escritura, GitHub te ofrecerá crear un *fork* y una
*pull request*: acéptalo y la organización lo revisará.

**Opción B — con git:**

```bash
git clone https://github.com/IAndreu/Online_School_2027.git
cd Online_School_2027

git checkout -b material-apellido
mkdir -p materials/sesion2/apellido-tema
cp -r ~/mis-diapositivas/* materials/sesion2/apellido-tema/

git add materials/sesion2/apellido-tema
git commit -m "Material de la sesión de [tema]"
git push -u origin material-apellido
```

Después abre una *pull request*. Una rama por ponente evita conflictos.

### Reglas prácticas

- **Nada de ficheros de más de 50 MB.** GitHub avisa a partir de 50 MB y rechaza
  a partir de 100 MB. Los datos grandes van a Classroom o a Zenodo, y en tu
  README pones el enlace y el checksum.
- **Sin acentos ni espacios en los nombres de fichero.** `practica-01.ipynb`, no
  `Práctica 1 (final).ipynb`.
- **Limpia la salida de los cuadernos** antes de subirlos
  (`jupyter nbconvert --clear-output --inplace tu-cuaderno.ipynb`).
- **PDF mejor que PPTX** para las diapositivas que se publiquen, salvo que
  quieras que se puedan editar.
- **Indica la licencia** de tu material en tu README. Si no indicas nada se
  asume que mantienes todos los derechos, lo que impide reutilizarlo en
  docencia — y ese es justamente el objetivo del curso.

---

## 3. Dar tu sesión en línea

Esto es lo que cambia respecto a una clase presencial. Nada es complicado, pero
casi todo se descubre tarde si no se prepara.

### La prueba técnica (no te la saltes)

La organización te propondrá una **prueba de 10–15 minutos** unas semanas antes.
Sirve para comprobar audio y compartir pantalla. El problema que aparece siempre
no es la plataforma: es que **la terminal o el IDE se ven ilegibles** al otro
lado.

### Que se vea tu terminal

Compartir una terminal para 30 personas, algunas en pantallas de 13 pulgadas,
exige preparación:

- **Letra grande, mucho más de la que te resulta cómoda a ti.** Como referencia,
  entre 16 y 20 pt en una pantalla de 1080p. Mira la miniatura de tu propia
  pantalla compartida: si tú no lo lees ahí, nadie lo lee.
- **Tema claro** (fondo blanco, texto oscuro). Aguanta mucho mejor la compresión
  de vídeo que un tema oscuro.
- **Comparte solo una ventana**, no el escritorio completo. Evita enseñar correo,
  notificaciones o nombres de ficheros que no tocan.
- **Ventana estrecha y alta** antes que ancha: el texto que se parte en dos
  líneas es difícil de seguir.
- Si usas Jupyter o RStudio, **aumenta el zoom del navegador** (Ctrl/Cmd + +).
- Silencia las notificaciones del sistema antes de empezar.

### Ritmo y participación

Tres horas y media de clase por videollamada cansan más que en persona, y la
atención se pierde sin que te des cuenta porque no ves las caras del fondo.

- **La pausa es de 16:30 a 16:45.** Úsala, y si la sesión se complica, añade otra
  breve.
- **Pregunta explícitamente.** "¿Alguna duda?" por videollamada suele recibir
  silencio. Funciona mucho mejor algo concreto: "poned en el chat qué os ha
  devuelto el comando", o "levantad la mano quien ya tenga el fichero generado".
- **Marca los puntos de control** en la práctica: momentos donde todo el grupo
  debe tener el mismo resultado antes de seguir. Sin ellos es imposible saber si
  alguien se quedó atrás hace veinte minutos. La plantilla de README tiene una
  tabla para esto.
- **Aprovecha el chat.** Pega ahí los comandos largos en lugar de dictarlos: se
  copian y evitas erratas. Alguien de la organización estará atento al chat
  mientras tú explicas.

### Material pensado para pantalla

- **Sube las diapositivas a Classroom antes de la sesión**, no después.
- En el guion de prácticas, **numera los pasos** y pon los comandos en bloques
  copiables. En línea, "como hicimos antes" no funciona: la gente se reincorpora
  a mitad.
- Incluye el **resultado esperado** de cada paso clave ("deberías ver 4 ficheros
  .bam"), para que cada persona compruebe por sí misma que va bien.

### Grabaciones

La organización decidirá si se graban las sesiones y te lo preguntará al
confirmar la tuya. **Puedes negarte**, y es una posición perfectamente legítima.
Si se graba, lo habitual será grabar solo la parte teórica, no la práctica ni los
turnos de preguntas.

### Si algo falla

- Entra **10 minutos antes** de tu hora. La sala no se abre para el grupo hasta
  que entra alguien del profesorado: hasta entonces esperan en la sala de espera.
- Habrá una persona de la organización en tu clase y un teléfono de contacto para
  incidencias; lo recibirás antes del curso.
- Si se te cae la conexión, no improvises: la organización avisa al grupo en
  Classroom y reanudáis. Está previsto.

---

## 4. Requisitos de software para las prácticas

Si tu sesión necesita software concreto en el entorno de prácticas, comunícalo a
la organización **con un mes de antelación**, indicando:

- Paquetes y versiones (idealmente un `environment.yml` de conda, un
  `requirements.txt`, o una imagen de contenedor).
- Recursos: memoria y CPU aproximados por participante.
- Datos que haya que precargar y su tamaño.

Escribe a **conexion-bcb@csic.es** con el asunto `[Escuela Online 2027] Software`.

---

## 5. A quién preguntar

- **Dudas sobre el repositorio o el sitio web:** abre una *issue* en GitHub.
- **Dudas sobre Classroom, Meet o problemas de acceso:** conexion-bcb@csic.es
- **Dudas sobre el programa o los horarios:** contacta con la coordinación.
