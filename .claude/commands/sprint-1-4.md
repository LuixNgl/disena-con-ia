# Sprint 1.4: Prompt de diseño

¡Bienvenido al último sub-sprint del Sprint 1!

Este sprint es especial: vamos a repasar lo aprendido hasta ahora y crear el **resultado clave** de todo el Sprint 1 — el prompt de diseño que usaremos para generar propuestas visuales de PeopleOnBoard.

Este sprint dura unos **20 minutos** y al final tendrás el briefing de diseño más completo que hayas creado.

STOP: ¿Cerramos el Sprint 1?

USER: Sí / Vamos / Adelante

---

## Revisar lo que tenemos

Antes de crear el prompt, repasemos los inputs que hemos generado en los sprints anteriores. Pídeme que lea los archivos y te resuma los insights clave:

```
Lee outputs/sintesis-entrevistas.md y outputs/analisis-competencia.md y resume los insights clave
```

STOP: Introduce el prompt o dime que lo ejecute.

USER: Lee outputs/sintesis-entrevistas.md y outputs/analisis-competencia.md y resume los insights clave

---

ACTION: Lee los archivos `PeopleOnBoard/outputs/sintesis-entrevistas.md` y `PeopleOnBoard/outputs/analisis-competencia.md`. Resume los insights clave del estudiante en bullets, organizados en dos bloques: "De la síntesis de entrevistas" y "Del análisis de competencia" (3-4 bullets cada uno). Usa el contenido real de los archivos — no muestres un resumen genérico.

---

## Revisar la template del prompt

Antes de que tomes decisiones, ¿quieres ver la template que usaremos para el prompt de diseño?

Está en `materiales/Template_Prompt_Diseno.md`. Puedes abrirla desde el explorador lateral o pedirme que la abra.

Hay algo que quizá quieras ajustar: la template tiene **Inter** como tipografía por defecto. Podemos cambiarla por un campo abierto para que elijas otra fuente más adelante.

STOP: ¿Abro la template para revisarla y la ajustamos?

USER: Sí / Ábrela / No, continuemos

---

## [Si quiere revisar la template]

ACTION: Abre el archivo `materiales/Template_Prompt_Diseno.md` en el editor

Ahí la tienes. Busca la sección de tipografía — verás que tiene Inter hardcodeada.

Te recomiendo cambiarla por un campo abierto. Así la template será reutilizable en otros proyectos, sin quedar atada a una fuente concreta.

Tienes dos opciones:
1. **Pídeme el cambio:** "Cambia la tipografía Inter por un campo abierto para elegir"
2. **Hazlo tú directamente:** Edita el archivo, guarda con `Cmd + S` (Mac) o `Ctrl + S` (Windows), y vuelve aquí

**Importante:** Si editas el archivo a mano, recuerda guardar (`Cmd + S` / `Ctrl + S`) **antes** de pedirme cualquier cambio. Si no, Cursor puede detectar inconsistencias entre tu versión y la mía.

STOP: ¿Cambiamos la tipografía por un campo abierto?

USER: Sí / No / [Cualquier respuesta]

---

## [Si quiere modificar la tipografía]

ACTION: Antes de modificar, recuerda al estudiante que guarde cualquier cambio manual que haya hecho en la template (`Cmd + S` / `Ctrl + S`). Luego modifica la template para cambiar la tipografía hardcodeada Inter por un placeholder que indique "Tipografía elegida por el usuario: sistema o Google Fonts (compatible con html.to.design)"

Listo. Ahora la tipografía quedará definida por tu elección en las siguientes preguntas.

---

## [Si el estudiante reporta inconsistencias o conflictos al guardar]

ACTION: Guíale paso a paso para resolver el conflicto en Cursor. Ver sección "Cambios No Guardados y Conflictos en Cursor" en CLAUDE.md del agente instructor.

---

## [Si prefiere no modificar la template]

Entiendo. Solo un apunte: si cambias Inter por un campo abierto, esta template te servirá para cualquier proyecto, no solo para PeopleOnBoard. Es un cambio pequeño que la hace mucho más versátil. ¿La modificamos?

STOP: [Esperar respuesta]

USER: Sí / No

---

## [Si acepta tras la insistencia]

ACTION: Modifica la template como se describe arriba (cambiar Inter por placeholder abierto).

---

## [Si sigue sin querer modificar]

Sin problema. Cuando generemos el prompt final, la tipografía que elijas en las siguientes preguntas se aplicará igualmente, no quedará limitada a Inter.

---

## Definir preferencias de diseño

Ahora necesito que tomes algunas decisiones de diseño. Vamos a usar de nuevo **AskUserQuestion** — la función que te muestra opciones para elegir.

Serán dos bloques de preguntas rápidas.

ACTION: Usa AskUserQuestion en 2 bloques

**Bloque 1 — Alcance y plataforma (2 preguntas):**

Pregunta 1: ¿Qué vista diseñamos para el MVP?
- Vista de empleado (fichaje diario) — Recomendada, es la interacción más frecuente
- Vista de manager (aprobar solicitudes)
- Vista de admin/RRHH (configuración y reportes)

Pregunta 2: ¿Para qué dispositivo diseñamos?
- Desktop — Los usuarios de PeopleOnBoard empiezan su jornada abriendo el portátil (Recomendada)
- Mobile — La pantalla se diseña para móvil

[Nota: La elección determina qué pantalla única generará el prompt. No diseñamos ambas versiones — eso vendría después del MVP.]

**Bloque 2 — Dirección visual (4 preguntas):**

Pregunta 3: ¿Qué estilo visual encaja mejor con PeopleOnBoard?
- Minimalista y limpio — Espacios amplios, pocos elementos
- Moderno y colorido — Gradientes, colores vibrantes
- Profesional y sobrio — Corporativo, transmite confianza
- Cálido y cercano — Ilustraciones, tono humano

Pregunta 4: ¿Qué estilo de tipografía prefieres?
- Sans-serif moderna (Inter, Geist) — Limpia y neutral
- Sans-serif geométrica (Poppins, Outfit) — Moderna y amigable
- Sans-serif humanista (Open Sans, Source Sans) — Cálida y legible
- Tengo una en mente (especificar)

Pregunta 5: ¿Qué familia de colores prefieres?
- Azules corporativos — Confianza, profesionalidad
- Verdes frescos — Modernidad, calma
- Neutros elegantes — Sofisticación, atemporalidad
- Proponer una paleta custom

Pregunta 6: ¿Tienes alguna web o app de referencia para el estilo visual?
- No, confío en tu criterio
- Estilo de librería de componentes (shadcn/ui, Radix) — Accesible, funcional, bien estructurado
- Sí, tengo una referencia (especificar URL)

[Esperar respuestas del usuario]

---

## [Después de recibir todas las respuestas]

Perfecto. Ya tengo todo lo necesario para crear el prompt de diseño.

Este prompt compilará:
- El contexto del producto
- Los insights de usuarios
- El posicionamiento frente a la competencia
- Todas las preferencias que acabas de elegir
- Los requisitos técnicos para html.to.design

**Nota:** Este análisis es más complejo que los anteriores — combina varios documentos y genera un brief detallado. Tardará un poco más de lo habitual.

Aquí está el prompt:

```
Genera el prompt de diseño usando la template materiales/Template_Prompt_Diseno.md. Incorpora el contexto de PRODUCTO.md, los insights de sintesis-entrevistas.md, el posicionamiento de analisis-competencia.md, y las preferencias que acabo de elegir. Guárdalo en PeopleOnBoard/outputs/prompt-diseno.md
```

STOP: Introduce el prompt o dime que lo ejecute.

USER: Genera el prompt de diseño usando la template materiales/Template_Prompt_Diseno.md. Incorpora el contexto de PRODUCTO.md, los insights de sintesis-entrevistas.md, el posicionamiento de analisis-competencia.md, y las preferencias que acabo de elegir. Guárdalo en PeopleOnBoard/outputs/prompt-diseno.md

---

ACTION: Genera el prompt de diseño usando el template `materiales/Template_Prompt_Diseno.md`, incorporando:
- Contexto del producto (de contexto-empresa/PRODUCTO.md)
- Insights de usuarios (de outputs/sintesis-entrevistas.md)
- Posicionamiento vs competencia (de outputs/analisis-competencia.md)
- Preferencias que acaba de elegir el usuario
- Requisitos técnicos para html.to.design (ver sección del template)
- **Tipografía:** Usa la elección del estudiante (Pregunta 4), independientemente de si modificó la template o no. Si la template aún tiene Inter hardcodeada, aplica la elección del estudiante en el prompt final.
- **Dispositivo:** Genera el prompt solo para el dispositivo elegido (Pregunta 2) — una pantalla, no dos.

Guarda el resultado en `PeopleOnBoard/outputs/prompt-diseno.md`

[Después de crear el archivo]

---

## El prompt de diseño

¡Archivo creado!

Mira lo que tienes ahora: un **briefing de diseño profesional** que incluye contexto del negocio, insights de research, dirección artística y especificaciones técnicas — todo en un solo documento, generado en minutos.

Este es exactamente el tipo de entregable que normalmente lleva horas de trabajo manual. Tú has dirigido todo el proceso: elegiste las preferencias, revisaste la template, y diste las instrucciones. La IA ejecutó el trabajo pesado.

STOP: ¿Quieres revisar el documento?

USER: Sí / Veámoslo / Muéstramelo

---

## [Si quiere revisar]

ACTION: Abre `PeopleOnBoard/outputs/prompt-diseno.md` en el editor

Recuerda: clic derecho en la pestaña → **Open Preview** para verlo con formato.

El documento tiene estas secciones:
1. **Contexto del Proyecto** — Qué es PeopleOnBoard y por qué existe
2. **Usuario Objetivo** — Basado en la síntesis de entrevistas
3. **Alcance del MVP** — Solo la pantalla de fichaje
4. **Dirección Artística** — Estilo, colores, tipografía, referencias
5. **Requisitos Técnicos** — Especificaciones para html.to.design

¿Hay algo que quieras ajustar?

STOP: [Esperar respuesta]

USER: No / Está bien / Perfecto

## [Si no quiere revisar]

Perfecto, lo tienes guardado en `outputs/prompt-diseno.md` para cuando lo necesites.

---

## Cierre del sprint 1

¡Enhorabuena! Has completado el Sprint 1 y estás aumentando tus superpoderes como Product Designer.

Piensa en lo que acabas de hacer: en cuestión de sprints has sintetizado entrevistas de usuario, analizado la competencia y creado un briefing de diseño profesional — todo dirigido por ti, ejecutado con IA.

**Lo que has producido:**

| Archivo | Contenido |
|---------|-----------|
| `outputs/sintesis-entrevistas.md` | Síntesis de research con insights de usuarios |
| `outputs/analisis-competencia.md` | Análisis comparativo del mercado |
| `outputs/prompt-diseno.md` | Brief de diseño profesional listo para usar |

**Lo que has aprendido:**

| Concepto | Para qué sirve |
|----------|----------------|
| IDE vs chat web | Cursor + terminal permiten gestionar archivos directamente |
| Referenciar con `@` | Acceso rápido a archivos desde el chat |
| Análisis de webs | Claude puede extraer información de páginas públicas |
| Sub-agentes | Tareas paralelas para optimizar tiempo y recursos |
| AskUserQuestion | Responder con opciones estructuradas |
| Templates reutilizables | Las de `materiales/` sirven para tus propios proyectos |
| Prompts específicos | Indicar rutas y acciones concretas da mejores resultados |
| Markdown preview | Ver documentos con formato en Cursor |

**Filosofía reforzada:**
- MVP mínimo: solo la pantalla de fichaje
- Validar rápido antes de expandir scope
- Tú diriges, la IA ejecuta

STOP: ¿Continuamos con lo que viene en el Sprint 2?

USER: Sí / Continuamos / Adelante

---

## Próximos pasos: Sprint 2

En el Sprint 2 usaremos este prompt para generar propuestas visuales reales.

Así funcionará:
1. Generaremos **4 opciones de HTML** con estilos diferentes
2. Cada opción será una interpretación distinta del brief
3. Podrás elegir una, mezclar elementos de varias, o iterar
4. El HTML cumplirá requisitos técnicos específicos:
   - **Pixel perfect** — Alineación precisa
   - **Dispositivo elegido** — Desktop (1440px) o mobile (390px)
   - **Base-8** — Sistema de espaciado consistente
   - **Light + Dark mode** — Ambos modos desde el inicio
   - **Accesibilidad** — WCAG 2.1 AA + EN 301 549
   - **Variables CSS tokenizadas** — Preparado para escalar

5. Usaremos **html.to.design** para convertir el HTML elegido a Figma
6. Configuraremos el plugin para que importe con **variables y estilos de Figma**: colores, espaciados, tipografía
7. El plugin importará con **auto-layout y variables ya aplicados**

---

Tómate un descanso si lo necesitas. Cuando estés listo, el Sprint 2 te espera con la parte más visual del curso.

**Recordatorio:** Si cierras Cursor, para retomar donde lo dejaste escribe `claude --continue` en la terminal. También puedes escribir `claude` y luego `/sprint-2-1` para ir directamente al Sprint 2.

STOP: Escribe `/sprint-2-1` para empezar el Sprint 2: Diseño.

USER: /sprint-2-1

---

## Notas para Claude (No mostrar al estudiante)

### Sobre la revisión de la template
- Si el usuario quiere modificar la tipografía, hazlo de forma que quede como placeholder editable
- Si no quiere modificar, insiste una vez — es buena práctica para reutilización de templates
- Si aún así rechaza, respeta la decisión. La tipografía que elija en las preguntas de diseño se aplicará igualmente al generar el prompt final
- **Cambios manuales:** Si el usuario edita la template a mano, recuérdale que guarde antes de pedirte cambios. Si ya se ha producido un conflicto, guíale con la vista comparativa de Cursor (ver sección "Cambios No Guardados y Conflictos en Cursor" en el CLAUDE.md del agente instructor)

### Sobre las preferencias de diseño
- La vista recomendada es "empleado (fichaje)" porque es el uso más frecuente
- Desktop es la recomendación (los usuarios empiezan su jornada abriendo el portátil), pero mobile es válido si el usuario lo prefiere
- La elección de dispositivo determina qué pantalla única se genera — no diseñamos ambas versiones en el MVP
- El estilo depende del target — para PYMES, "minimalista y limpio" o "cálido y cercano" suelen funcionar bien
- Si el usuario elige shadcn/ui / Radix como referencia, úsalo como **inspiración visual** en la Art Direction (limpio, accesible, bien estructurado) — no como dependencia técnica. El HTML generado debe ser siempre HTML/CSS puro, nunca React ni JSX.
- Si el usuario tiene una referencia web propia, incorpórala en el prompt

### Sobre el prompt de diseño
- Asegúrate de incluir TODOS los requisitos técnicos para html.to.design:
  - Pixel perfect
  - Responsive (mobile-first o según elección)
  - Base-8 spacing
  - Light + Dark mode
  - WCAG 2.1 AA + EN 301 549
  - Variables CSS tokenizadas
  - HTML semántico
- Estos requisitos son críticos para que el HTML se importe bien a Figma

### Sobre html.to.design y componentes
- Con la configuración recomendada (que se activa en Sprint 2.1), el plugin importa: auto-layout, variables y estilos locales, nombres de capa del HTML, componentes hover, y hyperlinks
- Lo que NO importa: un Design System completo (componentes maestros, variantes más allá de hover, documentación)
- Si el usuario pregunta por Design System, explica que es un paso posterior al MVP

### Sobre el cierre
- Este es un buen momento para recomendar un descanso
- El Sprint 2 es más visual y práctico
- Si el usuario tiene preguntas pendientes, resuélvelas antes de cerrar

## Criterios de Éxito

- [ ] Estudiante ha revisado los insights de sprints anteriores
- [ ] Estudiante ha tenido oportunidad de revisar/modificar la template
- [ ] Estudiante eligió preferencias de diseño (vista, dispositivo, estilo, tipografía, colores, referencias)
- [ ] Se ha creado `outputs/prompt-diseno.md` con el brief completo
- [ ] Estudiante entiende los próximos pasos (4 HTMLs → html.to.design → Figma)
- [ ] Estudiante sabe que el plugin importa auto-layout y variables
- [ ] Estudiante sabe cómo retomar el curso si cierra Cursor
