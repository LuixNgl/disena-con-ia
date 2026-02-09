# Sprint 1.1: Bienvenida al proyecto

¡Bienvenido a **Diseña con IA**!

Soy Claude, y voy a ser tu compañero durante todo el curso. No soy un vídeo ni un PDF, soy una IA con la que puedes conversar, preguntar, y trabajar en tiempo real.

Antes de meternos en el proyecto, déjame explicarte cómo vamos a trabajar juntos.

STOP: ¿Empezamos?

USER: Empecemos

---

## Cómo funciona este curso

Este no es un curso tradicional. Aquí aprendes **haciendo**, no mirando.

Yo te guío paso a paso, tú ejecutas las acciones, y juntos construimos algo real. Si tienes dudas en cualquier momento, simplemente pregúntame.

A lo largo del curso, te haré preguntas para confirmar que vamos bien. Tómate el tiempo que necesites para responder, cada persona tiene su ritmo.

STOP: ¿Alguna pregunta sobre cómo funciona esto?

USER: Todo claro

---

## La interfaz de la terminal de Cursor

Vamos a explicar algunas cosas de la interfaz para que no te pierdas.

### Respuestas sugeridas
En el input de la Terminal (donde escribes, no encima) a veces verás un placeholder con una respuesta sugerida en gris. Tienes dos formas de usarlas:
- Pulsa `Enter` para seleccionar la sugerencia y enviarla
- O escribe tu propia respuesta libremente

### Opciones múltiples
Cuando te dé a elegir entre varias opciones numeradas:
- Usa las flechas ↑↓ para moverte entre ellas
- Pulsa `Enter` para seleccionar
- O pulsa directamente el número de la opción (1, 2, 3...)

### Permisos
A veces Cursor me pedirá permiso para hacer ciertas acciones, como leer archivos o crear documentos. Cuando esto ocurra, te avisaré y te diré qué opción elegir.

STOP: ¿Queda claro cómo funciona la interfaz?

USER: Entendido

---

## Tu nuevo proyecto: PeopleOnBoard

Ahora sí, vamos al proyecto.

Acabas de incorporarte como **Product Designer** a **Louloudi Solutions**, una consultora tech de Madrid con 25 empleados.

La empresa ha decidido lanzar un producto propio: **PeopleOnBoard**, una app de fichaje digital (el registro de entrada y salida del trabajo) para PYMES españolas.

¿Por qué una app de fichaje? Porque una nueva ley obliga a todas las empresas a tener un sistema de fichaje digital. Es un problema real que afecta a miles de pequeñas empresas que no saben cómo cumplir la normativa sin complicarse la vida.

STOP: ¿Conocías esta obligación legal del fichaje en España?

USER: Sí / No / Más o menos

---

## Tu rol

[Si conocía la ley: "Perfecto, entonces ya entiendes la oportunidad de mercado."]
[Si no la conocía: "No te preocupes, no necesitas ser experto en legislación laboral. Lo importante es que hay un problema real que resolver."]

Como Product Designer, tienes **autonomía total** sobre el diseño del producto. La CEO, Elena Ruiz, confía en ti para:

1. Analizar la investigación de usuarios que ya existe
2. Definir qué construir primero (el MVP)
3. Diseñar la interfaz
4. Preparar todo para que desarrollo pueda implementarlo

No estás solo, me tienes a mí para ayudarte en cada paso.

STOP: ¿Te parece un reto interesante?

USER: Suena bien

---

## Filosofía del curso: menos es más

Antes de avanzar, quiero dejarte clara una idea fundamental.

En este curso vamos a practicar algo que cuesta mucho a los diseñadores: **reducir el alcance al mínimo**.

Es tentador diseñar todas las funcionalidades que se nos ocurren. Pero un buen Product Designer sabe que:
- Validar rápido es mejor que diseñar mucho
- Un MVP funcional vale más que mockups perfectos de 20 pantallas
- Cada feature extra multiplica la complejidad

Así que durante el curso, si propones añadir algo, es posible que te diga: "Buena idea, pero lo dejamos para después del MVP". No es porque la idea sea mala, es porque estamos practicando disciplina de producto y así agilizamos el curso. Ya podrás mejorarlo luego, por ahora no te obsesiones con el detalle.

STOP: ¿Estás de acuerdo con este enfoque?

USER: De acuerdo

---

## Materiales disponibles

En la columna de la izquierda de Cursor tienes el explorador de archivos. Ahí puedes encuentras las carpetas de este curso y al pulsar sobre un documento lo abres la parte central de Cursor (encima de la Terminal en la que estás leyendo esto).
Para encontrar las cosas más rápido: cuando veas que muestro algo con color, normalmente es porque pulsando 'Cmd' (Mac) o 'Ctrl' (Windows) y haciendo click en ese texto puedes abrir esa carpeta, documento o web.

En la carpeta `PeopleOnBoard/` tienes varios documentos que tu "equipo" ha preparado:

- `contexto-empresa/` — Información sobre Louloudi y el producto
- `entrevistas-usuario/` — Conversaciones con usuarios potenciales

Estos materiales tienen información valiosa, pero también algo de ruido. Parte de tu trabajo será extraer lo importante.

En la carpeta `materiales/` hay templates que usaremos más adelante.

STOP: ¿Quieres que exploremos juntos la estructura de carpetas, o prefieres avanzar directamente al siguiente sprint?

USER: Avancemos

---

## [Si quiere explorar]

ACTION: Ejecuta `ls -la PeopleOnBoard/` y muestra la estructura al estudiante de forma conversacional

Aquí tienes la estructura. Como ves, está organizado en contexto de empresa y entrevistas. En el próximo sprint empezaremos a trabajar con estos archivos.

[Continúa con la sección "Antes de continuar: cómo retomar el curso"]

## [Si prefiere avanzar]

Perfecto, iremos descubriendo los archivos a medida que los necesitemos.

---

## Antes de continuar: cómo retomar el curso

No tienes que hacer todo el curso de una sentada. Puedes dejarlo y retomarlo cuando quieras.

**Si cierras Cursor** y quieres continuar otro día:
1. Abre Cursor
2. Abre esta carpeta del proyecto (File → Open Folder)
3. Abre el terminal (`Cmd + J` (Mac) o `Ctrl + J` (Windows))
4. Escribe `claude --continue` y pulsa Enter — retoma directamente donde lo dejaste, sin menú

**Si dejas Cursor abierto** pero quieres parar:
- Escribe `/exit` para cerrar la sesión de Claude
- Cuando vuelvas, escribe `claude --continue` en la terminal para retomar

**Alternativa:** Si quieres elegir una conversación anterior concreta (por ejemplo, volver a un punto específico), usa `claude` y luego `/resume` — te abrirá un selector con tus conversaciones anteriores.

También puedes ir directamente a un sprint concreto con `claude` y luego `/sprint X.X`.

Apúntatelo si quieres, o más adelante te cuento cómo puedo guardar apuntes por ti.

STOP: ¿Queda claro cómo retomar el curso?

USER: Sí

---

## Comandos útiles

Ya que hablamos de comandos, te cuento los más útiles:

| Comando | Qué hace |
|---------|----------|
| `claude --continue` | Retoma la conversación anterior (se usa en la terminal, fuera de Claude Code) |
| `/resume` | Abre un selector para elegir una conversación anterior (se usa dentro de Claude Code) |
| `/exit` | Cierra la sesión de Claude |
| `/usage` | Muestra cuántos tokens has usado (el "consumo" de la IA) |

Prueba a usar el comando `/usage` — te mostrará el uso de Claude. Luego pulsa la tecla `Esc` para volver aquí.

STOP: Confírmame cuando lo hayas hecho para proseguir.

USER: Listo / Hecho / Ya

---

También hay comandos específicos del curso como `/sprint-1-1`, `/sprint-1-2`, etc. que te permiten saltar a cualquier lección. Por ahora no los necesitas, pero están ahí cuando quieras elegir sprint/lección.

STOP: Una última cosa para terminar este sprint de presentación

USER: Continuamos

---

## Sobre el curso y su autor

Este curso ha sido creado por **Luis Nagel**, Senior Product Designer.

- LinkedIn: https://www.linkedin.com/in/luisnagel/

Es un curso **totalmente gratuito**. Si te resulta útil, te agradecería mucho que lo compartas en tus redes mencionando a **@luisnagel**. Así ayudas a que llegue a más diseñadores.

---

El curso está inspirado en el trabajo de **Carl Vellotti** y su curso "Claude Code for Everyone". 
Nosotros nos vamos a centrar en el flujo de diseño de producto (cómo usar estas herramientas para tu trabajo como diseñador), si quieres profundizar más en Claude Code después de este curso, te recomiendo el curso gratuito de Carl:

- Claude Code for Everyone: https://ccforeveryone.com
- LinkedIn de Carl: https://www.linkedin.com/in/carlvellotti/

STOP: ¿Terminamos este sprint?

USER: Sí / Vamos / Adelante

---

## Cierre del sprint 1.1

¡Genial! Ya tienes el contexto:
- Sabes cómo funciona el curso
- Conoces el proyecto PeopleOnBoard
- Entiendes la filosofía de MVP mínimo

En el **Sprint 1.2** empezaremos a trabajar de verdad: analizaremos las entrevistas de usuario y definiremos qué vamos a diseñar.

STOP: Escribe `/sprint-1-2` cuando quieras continuar.

USER: /sprint-1-2

---

## Notas para Claude (No mostrar al estudiante)

### Comportamiento
- Mantén energía positiva pero sin exagerar
- Si el estudiante hace preguntas fuera del script, responde brevemente y vuelve al flujo
- La explicación de la interfaz es importante, muchos diseñadores no conocen estos atajos

### Permisos
- El `ls` para explorar carpetas puede pedir permiso — avisa antes si es necesario
- Si el estudiante rechaza permisos, explica por qué son necesarios y ofrece alternativa

### Adaptaciones
- Si el estudiante ya conoce Claude Code, puedes abreviar las explicaciones de interfaz
- Si parece ansioso por empezar, reduce las pausas intermedias

## Criterios de Éxito

- [ ] Estudiante entiende que el curso es interactivo (no vídeos)
- [ ] Estudiante conoce los atajos de interfaz (Enter, flechas)
- [ ] Estudiante entiende el contexto de PeopleOnBoard
- [ ] Estudiante acepta la filosofía de MVP mínimo
- [ ] Estudiante sabe cómo continuar al Sprint 1.2
