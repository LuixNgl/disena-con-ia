# Sprint 1.3: Análisis de competencia

Ahora que entendemos a nuestros usuarios, vamos a ver qué ofrece el mercado.

No diseñamos en el vacío, necesitamos saber contra quién competimos y dónde están las oportunidades.

Este sprint dura unos **15 minutos** y al final tendrás un análisis comparativo del mercado.

STOP: ¿Continuamos?

USER: Sí / Adelante / Continuamos

---

## Identificar la competencia

Yo podría buscar desde cero cuáles son los principales competidores de PeopleOnBoard en España: analizar el mercado, filtrar por relevancia y proponerte una selección. Eso es algo que la IA hace muy bien.

Pero para agilizar, tu equipo ya ha identificado a los dos jugadores principales en HR software para PYMES:

1. **Factorial HR** (factorial.es) — Líder del mercado español, muy completo
2. **Sesame HR** (sesamehr.es) — Más enfocado en control horario

STOP: ¿Has usado alguno de estos productos?

USER: Sí / No / He oído hablar de ellos

---

## [Si ha usado alguno]

Genial, entonces ya tienes contexto. Aun así, vamos a hacer un análisis estructurado para tener todo documentado.

## [Si no los conoce]

No te preocupes, vamos a analizarlos juntos.

---

## La template de análisis

En la carpeta `materiales/` tienes una template para análisis de competencia. Por cierto, todas las templates de esa carpeta son reutilizables — guárdalas para tus propios proyectos fuera de este curso.

### Sub-agentes

Para ver la competencia necesito acceder a sus webs. Cuando analizo varias webs a la vez, Claude Code puede lanzar **sub-agentes** — asistentes especializados que trabajan en paralelo en una misma tarea o serie de tareas. Mientras uno analiza Factorial, otro analiza Sesame al mismo tiempo. Esto ahorra tiempo y optimiza recursos.

Los sub-agentes funcionan bien para tareas independientes e identicas en el proceso. Cuando las tareas comparten contexto o datos vinculados entre sí, se usa un **agente principal**, como el definido en el archivo `CLAUDE.md` de este curso, que mantiene la coherencia de todo. Si quieres profundizar en cómo funcionan los agentes y sub-agentes, el curso de Carl Vellotti entra en mucho más detalle.

### Permisos de acceso web

Cursor me pedirá **permiso para acceder a cada web** — verás la petición una vez por cada sitio. Igual que antes, elige **Allow** o **Always allow**.

### El prompt

Ahora sí, vamos a ejecutar el análisis. Fíjate en cómo está estructurado el prompt — indica qué analizar, qué template seguir, y dónde guardar el resultado:

```
Analiza las webs factorial.es y sesamehr.es siguiendo la template materiales/Template_Analisis_Competencia.md. Guarda el resultado en PeopleOnBoard/outputs/analisis-competencia.md
```

STOP: Escribe el prompt o dime que lo ejecute.

USER: Analiza las webs factorial.es y sesamehr.es siguiendo la template materiales/Template_Analisis_Competencia.md. Guarda el resultado en PeopleOnBoard/outputs/analisis-competencia.md

---

ACTION: Analiza en paralelo las webs de factorial.es y sesamehr.es usando el template `materiales/Template_Analisis_Competencia.md`. Extrae: posicionamiento, target, precios (si están públicos), funcionalidades core, estilo visual, y diferenciadores. Guárdalo en `PeopleOnBoard/outputs/analisis-competencia.md`

[Después de crear el archivo]

¡Archivo creado! Ya tienes tu análisis de competencia en `outputs/analisis-competencia.md`.

Fíjate en lo que acabas de hacer con un solo prompt: has analizado dos productos de la competencia, extraído información de sus webs y generado un documento comparativo estructurado.

Ábrelo desde el explorador de la izquierda: `PeopleOnBoard/outputs/analisis-competencia.md`. Recuerda: clic derecho en la pestaña → **Open Preview** para verlo renderizado.

STOP: Abre el archivo y revísalo. Cuando termines, vuelve a la terminal para continuar.

USER: Listo / Ya lo he visto / Hecho

---

## Completar con datos de PeopleOnBoard

Para completar la matriz necesitamos los datos de PeopleOnBoard. Aquí voy a usar una funcionalidad llamada **AskUserQuestion** — me permite hacerte preguntas con opciones predefinidas.

En lugar de que escribas texto libre, te mostraré opciones para elegir. Es más rápido y me permite estructurar mejor la información. Verás las opciones numeradas — puedes pulsar el número directamente o usar las flechas.

A veces verás una última opción **"Type something else"** — si la eliges, puedes escribir tu propia respuesta en lugar de usar las predefinidas.

Después de responder, la terminal te pedirá permiso para enviar las respuestas. Elige **1. Yes** para continuar. Y luego necesitaré **permiso para actualizar el archivo** — como antes: **Allow** o **Always allow**.

ACTION: Usa AskUserQuestion para preguntar las siguientes preferencias en batches:

**Batch 1:**
- ¿Cuál sería el tagline o claim de PeopleOnBoard?
  - "Fichaje simple y rápido" (Recomendada)
  - "Tu equipo, conectado"
  - "El fichaje que tu PYME necesita"
  - Tengo otra idea

**Batch 2:**
- ¿Qué estilo visual prefieres para PeopleOnBoard?
  - Minimalista y limpio — Menos es más
  - Moderno y colorido — Energía y dinamismo
  - Profesional y sobrio — Confianza corporativa
  - Cálido y cercano — Humano y accesible

[Esperar respuestas del usuario]

---

## [Después de recibir respuestas]

Perfecto. Con esta información ya puedo completar la columna de PeopleOnBoard.

ACTION: Actualiza `PeopleOnBoard/outputs/analisis-competencia.md` con los datos de PeopleOnBoard

---

## Oportunidades identificadas

Mirando la comparativa, hay algunas oportunidades claras para PeopleOnBoard:

1. **Simplicidad radical** — Factorial es muy completo pero puede abrumar. Sesame es simple pero básico. Hay espacio para "simple pero bonito".

2. **Buena experiencia móvil** — La competencia tiene apps móviles pero con experiencia mejorable. PeopleOnBoard puede diferenciarse ofreciendo una experiencia móvil realmente cuidada como complemento al uso principal en desktop.

3. **Precio/valor** — Las gestorías laborales como canal de distribución pueden permitir precios más competitivos.

4. **Foco en fichaje + conexión** — Ni Factorial ni Sesame se enfocan en hacer del fichaje un momento de conexión con la empresa (aunque eso queda fuera del MVP).

STOP: ¿Alguna observación o pregunta sobre el análisis?

USER: No / Todo claro / Continuemos

---

## Cierre del sprint 1.3

Ya conoces el terreno de juego.

**Lo que has aprendido:**
- Cómo pedir a Claude que analice webs de la competencia
- Cómo funcionan los sub-agentes y el procesamiento en paralelo
- Cómo funciona **AskUserQuestion** para responder con opciones estructuradas
- Que las templates de `materiales/` son reutilizables en tus proyectos

**Lo que has producido:**
- `outputs/analisis-competencia.md` — Matriz comparativa del mercado con datos de los tres productos

En el **Sprint 1.4** vamos a crear el prompt de diseño — el brief que usaremos para generar las primeras propuestas visuales de PeopleOnBoard.

STOP: Escribe `/sprint-1-4` cuando quieras.

USER: /sprint-1-4

---

## Notas para Claude (No mostrar al estudiante)

### Sobre el análisis web
- Los precios de Factorial y Sesame pueden no estar públicos o haber cambiado. Si no encuentras precios exactos, indica "Contactar para precio" o el rango aproximado si lo conoces
- Si WebFetch falla, menciona que a veces las webs bloquean scrapers y ofrece usar la info general que conoces del mercado

### Sobre las preguntas al usuario
- Usa AskUserQuestion con las opciones especificadas
- El tagline recomendado es "Fichaje simple y rápido" — si el usuario tiene otra idea, acéptala
- El estilo visual influirá en el prompt de diseño del Sprint 1.4

### Sobre los sub-agentes
- Menciona que usas sub-agentes, pero no te extiendas demasiado en la explicación técnica
- La referencia a Carl Vellotti es para quien quiera profundizar

### Datos de PeopleOnBoard para completar
- Posicionamiento: "Fichaje digital simple para PYMES españolas"
- Target principal: PYMES 10-50 empleados
- Canal: Gestorías laborales
- Diferencial: Simplicidad + buena experiencia en todos los dispositivos
- Los colores y estilo dependen de la respuesta del usuario

## Criterios de Éxito

- [ ] Estudiante entiende cómo pedir análisis de webs a Claude
- [ ] Estudiante entiende el concepto de sub-agentes/paralelismo
- [ ] Se ha creado `outputs/analisis-competencia.md` con datos de los 3 productos
- [ ] El usuario ha elegido tagline y estilo visual para PeopleOnBoard
- [ ] Estudiante conoce las oportunidades de diferenciación
