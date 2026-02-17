# Sprint 2.1: De prompt a Figma

Empezamos el Sprint 2, la parte más visual del curso.

En el Sprint 1 construiste los cimientos: research, análisis de competencia y un briefing de diseño profesional. Ahora vamos a convertir todo eso en propuestas de diseño reales.

El enfoque: primero explorar varias direcciones visuales en HTML (rápido, barato en tokens) y después llevar la elegida a Figma. En el siguiente sprint usaremos la IA para editar el diseño directamente en Figma, así que este paso nos sirve para llegar allí con una propuesta sólida y decisiones tomadas. Al final de este sub-sprint puedes tener:
- **4 propuestas de diseño** comparadas y una dirección elegida
- Tu propuesta **importada a Figma** como archivo editable con variables y auto-layout

Antes de empezar, un tip: escribe `/usage` para ver cuántos tokens te quedan en esta sesión. Así puedes controlar el uso a lo largo del Sprint 2, que es el más intensivo. Cuando hayas visto los datos de uso, pulsa `Esc` para volver aquí.

STOP: ¿Vamos a ver tus ideas cobrar forma?

USER: Sí / Vamos / Adelante

---

## Tus 4 propuestas de diseño

Tienes el briefing en `outputs/prompt-diseno.md`. Vamos a usarlo para generar **4 propuestas de diseño en HTML**, cada una con un estilo visual diferente para que puedas elegir y definir mejor el estilo.

¿Por qué HTML y no directamente Figma? Por dos razones principales:

1. **Velocidad y coste:** La IA genera 4 propuestas en HTML en cuestión de minutos y con un consumo de tokens bajo. Hacer lo mismo directamente en Figma (crear frames, estilos, componentes, auto-layout...) llevaría mucho más tiempo y tokens. HTML es un medio rápido y barato para explorar direcciones visuales.

2. **Mejores decisiones antes de Figma:** Cuando llegues a Figma, ya habrás elegido una dirección visual, descartado opciones y refinado tu propuesta. Llegas con decisiones tomadas, no a improvisar. Es similar a lo que hace un developer: no escribe código directamente, primero analiza el problema y define la solución.

Después usaremos un plugin llamado **html.to.design** que convierte HTML en diseños editables de Figma. El HTML es nuestro puente entre la IA y Figma, y así también aprovechamos mejor el freemium del plugin.

Aquí va el prompt:

```
Lee outputs/prompt-diseno.md y genera 4 propuestas de diseño en HTML para la pantalla de fichaje de PeopleOnBoard. Cada propuesta debe tener un estilo visual diferente, cumplir todos los requisitos técnicos del prompt, y guardarse en PeopleOnBoard/outputs/html-propuestas/ como opcion-1.html, opcion-2.html, opcion-3.html y opcion-4.html
```

**Aviso:** Esta acción puede tardar unos minutos, la IA está generando 4 propuestas completas con estilos distintos. Cursor te pedirá permiso para crear cada archivo. Selecciona **"Allow"** cuando te lo pida (o **"Allow All"** si prefieres agilizar).

STOP: Introduce el prompt o dime que lo ejecute.

USER: [prompt o "ejecuta"]

---

ACTION: Lee `PeopleOnBoard/outputs/prompt-diseno.md` y genera 4 archivos HTML en `PeopleOnBoard/outputs/html-propuestas/`:
- Cada archivo es una propuesta completa de la pantalla de fichaje de PeopleOnBoard
- Cada una con un estilo visual claramente distinto (basados en la dirección artística del prompt pero con variaciones de personalidad)
- Todas cumplen los requisitos técnicos del prompt: pixel perfect, base-8, light+dark mode, WCAG 2.1 AA, variables CSS tokenizadas, HTML semántico
- Genera solo para el dispositivo indicado en el prompt del estudiante (mobile o desktop), no ambos
- Los archivos deben ser HTML completo con CSS embebido, funcional al abrir en navegador
- Nombres: opcion-1.html, opcion-2.html, opcion-3.html, opcion-4.html
- Avisa al estudiante antes de crear cada archivo para que apruebe el permiso en Cursor

[Después de crear los 4 archivos]

¡Listo! Tienes 4 propuestas. Puedo mostrarlas todas en pestañas del navegador para que puedas compararlas.

STOP: ¿Las abro?

USER: Sí / Ábrelas / Adelante

---

ACTION: Abre los 4 archivos HTML en el navegador usando bash open

---

## Revisar y elegir

Tómate un momento para mirar las 4 opciones. Fíjate en la estructura, los colores, la tipografía y cómo se presenta el flujo de fichaje. Si tu navegador tiene modo oscuro, también podrás comparar el dark mode.

Cada propuesta es una interpretación diferente de tu briefing. Las 4 cumplen los mismos requisitos técnicos, la diferencia está en la personalidad visual.

¿Con cuál seguimos? Puedes:
- **Elegir una** y avanzar (la ajustaremos en Figma)
- **Combinar elementos** de varias (dime cuáles)
- **Pedir un cambio concreto** antes de avanzar

No hace falta que sea perfecta, los ajustes finos los harás en Figma, que es donde tu ojo de diseñador marca la diferencia. El objetivo es avanzar en el curso. En la práctica real, sí conviene refinar el HTML antes de Figma, pero aquí queremos agilizar.

STOP: ¿Con cuál seguimos?

USER: [Respuesta del estudiante]

---

ACTION: Según la elección del estudiante, genera `PeopleOnBoard/outputs/html-propuestas/propuesta-final.html`:
- Si elige una opción tal cual → Copia su contenido como propuesta-final.html
- Si quiere combinar o modificar → Crea propuesta-final.html con los cambios aplicados
No fomentes iteraciones extensas — mejor avanzar a Figma.

Voy a crear `propuesta-final.html` con tu elección.

[Después de crear el archivo]

Ya tienes la versión final. ¿La abro en el navegador para que la revises?

STOP: ¿La abro?

USER: Sí / Ábrela / Adelante

---

ACTION: Abre propuesta-final.html en el navegador usando bash open

¿Qué te parece? Si quieres algún ajuste, dime qué cambiar. Si está bien, seguimos.

STOP: ¿Seguimos o quieres algún cambio?

USER: Está bien / Perfecto / [Quiere cambios]

## [Si quiere cambios adicionales]

ACTION: Aplica los cambios en propuesta-final.html y vuelve a abrirla en el navegador para que el estudiante la revise.

---

Ahora mismo, junto a `propuesta-final.html` tienes las 4 propuestas previas. ¿Las elimino para quedarte solo con la elegida?

STOP: ¿Las elimino?

USER: Sí / No / Elimínalas

## [Si quiere eliminarlas]

ACTION: Elimina opcion-1.html a opcion-4.html. Mantén propuesta-final.html.

Listo, eliminadas. Solo queda `propuesta-final.html` en la carpeta.

## [Si prefiere conservarlas]

Sin problema, ahí se quedan.

---

## Lo que acabas de conseguir

Piensa en lo que ha pasado: has definido un briefing de diseño, y la IA ha generado 4 propuestas visuales profesionales a partir de él. Esto ya es muy útil para validar la dirección del producto con tu equipo.

Pero aquí va un matiz importante: hasta este punto, un PM con acceso a las mismas herramientas podría haber llegado al mismo resultado. **Tu valor como Product Designer se activa en el siguiente paso.** Cuando lleves esto a Figma y hagas ajustes de diseño que solo un ojo entrenado puede hacer: espaciados, jerarquía visual, consistencia del sistema, refinar la experiencia.

Por cierto: estos HTML también podrían ser interactivos, con transiciones y estados funcionales. Eso lo veremos más adelante.

Ahora vamos a llevar tu diseño a Figma.

STOP: ¿Continuamos?

USER: Sí / Vamos / Adelante

---

## De HTML a Figma

Existen varias formas de trabajar con Figma usando IA, las repasaremos al final del Sprint 2. Vamos a empezar con **html.to.design**, un plugin que convierte HTML en diseños editables de Figma. Es rápido, preciso y permite unos 10 usos gratis al mes ¡perfecto para lo que necesitamos ahora!

Primer paso: crea un nuevo archivo de **Figma Design** (no FigJam) y ponle nombre **PeopleOnBoard**.

STOP: Avísame cuando lo tengas.

USER: Listo / Creado / Ya está

---

Bien. Ahora necesitas el plugin **html.to.design**:

1. Búscalo en Figma → Resources → Plugins, o ve directo a [html.to.design en la comunidad de Figma](https://www.figma.com/community/plugin/1159123024924461424/html-to-design-by-divriots-import-websites-to-figma-designs-web-html-css)
2. Haz clic en **"Try it..."** y elige el documento que acabas de crear

STOP: ¿Lo tienes abierto?

USER: Sí / Listo / [Problema]

## [Si tiene problemas con el plugin]

ACTION: Ayuda al estudiante:
- No lo encuentra → Resources (icono de libro) → Plugins → buscar "html.to.design" → Run
- No carga → Verificar que es un archivo Figma Design, no FigJam
- No aparece "Save" → Puede que ya esté instalado

---

## Configurar html.to.design (MCP)

Ahora vamos a conectar la terminal de Cursor con el plugin html.to.design a través de MCP para poder enviar diseños directamente a Figma.

**MCP** (Model Context Protocol) es un estándar que permite a herramientas de IA comunicarse con aplicaciones externas. Piensa en él como un puente: lo configuras una vez y después puedo enviar diseños a Figma automáticamente desde aquí.

¿Por qué lo configuramos desde la terminal? Porque estamos trabajando en la terminal de Cursor, y configurar el MCP aquí nos permite enviar diseños a Figma sin cambiar de herramienta.

**Nota:** También se puede configurar desde el chat de Cursor o desde la app de Claude Desktop (válida incluso con planes gratuitos), son opciones igualmente válidas y sencillas. Otra opción es darle el código HTML directamente dentro del plugin en Figma, o usar su extensión de Chrome para convertir cualquier web.

Vamos paso a paso. Primero, la configuración en el plugin:

1. En Figma, dentro del plugin **html.to.design**, selecciona la pestaña **MCP**
2. Activa el toggle **Enable MCP endpoint**
3. Aparecerá un enlace **"how to configure your AI tool?"** (puede aparecer en español según tu configuración) — haz clic
4. Selecciona la pestaña **Other**
5. Copia la URL del primer bloque, la del servidor remoto, con formato `https://h2d-mcp.divriots.com/.../mcp`

STOP: ¿Tienes la URL copiada?

USER: Sí / Copiada / [Problema]

## [Si no encuentra la pestaña MCP o el toggle]

ACTION: Ayuda al estudiante:
- No ve pestaña MCP → Asegurarse de que el plugin está actualizado (desinstalar y reinstalar desde la comunidad de Figma)
- No ve el toggle → Puede estar en otra versión del plugin. Buscar "Enable" o "MCP" dentro de las opciones del plugin

---

Ahora pégame esa URL aquí para que pueda preparar el comando de configuración.

STOP: Pega la URL del plugin.

USER: [URL del plugin]

---

ACTION: El estudiante pega una URL. Valida que empiece por `https://h2d-mcp.divriots.com/` y termine en `/mcp`. Si el formato es correcto, genera el comando exacto y muéstralo al estudiante:

```
claude mcp add --transport http html-to-design "[URL_DEL_ESTUDIANTE]"
```

Si el formato NO es correcto:
- Pregunta si ha copiado la URL correcta (primer bloque, pestaña "Other")
- Ayúdale a encontrar la URL correcta en el plugin

---

Para ejecutar este comando, necesitas salir de Claude Code momentáneamente y volver a entrar:

1. Escribe `/exit` para cerrar esta sesión
2. En la terminal, ejecuta el comando: [repite aquí el comando exacto con la URL del estudiante que generaste en el paso anterior]
3. Escribe `claude --continue` para retomar la conversación donde la dejamos

No te preocupes, no perderás nada. `claude --continue` retoma exactamente donde lo dejaste.

STOP: ¿Has ejecutado el comando y vuelto con `claude --continue`?

USER: Sí / Listo / Hecho / [Problema]

## [Si tiene problemas con el comando MCP]

ACTION: Ayuda a resolver. Problemas comunes:
- Error al ejecutar el comando → Verificar que la URL está entre comillas y es correcta
- No reconoce `claude` → Verificar que Claude Code está instalado correctamente
- Quiere verificar que se ha añadido → Puede ejecutar `claude mcp list` para ver los servidores configurados
- Si el MCP no funciona tras varios intentos → Usar el plugin manualmente: pegar el HTML directamente en la pestaña "Code" del plugin dentro de Figma

---

## Configurar la importación

Antes de importar, vamos a activar unas opciones del plugin para que el resultado en Figma sea mucho más completo.

En el plugin html.to.design (que ya tienes abierto en Figma), cierra el modal **"MCP Configuration"** que probablemente tienes abierto y busca el botón **"Import configuration"** en la pestaña MCP. Al pulsarlo se despliegan las opciones de importación.

Activa estos toggles:

**Options:**
- [x] Use Autolayout (se activa por defecto con los siguientes)
- [x] Create styles & variables
- [x] Use existing local styles

**Components:**
- [x] For hover effects

**Enhancements:**
- [x] Add hyperlinks
- [x] HTML layer names

Los demás puedes dejarlos como están. Cuando estén activados, pulsa **Proceed** para confirmar y cerrar los ajustes. Puede que no te aparezca el botón **Proceed**, en ese caso cierra los ajustes de **"MCP Configuration"** directamente y asegúrate que estás en la pantalla principal del plugin.

¿Qué hacen?
- **Create local styles & variables** crea variables y estilos de Figma a partir de los valores del CSS (colores, tipografía, espaciados)
- **Use existing local styles** reutiliza estilos que ya existan en tu archivo (evita duplicados)
- **For hover effects** genera componentes con variantes hover a partir de los estados `:hover` del CSS
- **Add hyperlinks** mantiene los enlaces del HTML como hyperlinks en Figma
- **HTML layer names** nombra las capas con las clases del HTML en vez de nombres genéricos

STOP: ¿Has activado las 5 opciones?

USER: Sí / Listo / Activadas

## [Si no encuentra "Import configuration"]

ACTION: Ayuda al estudiante:
- No ve el botón → Puede estar en la parte inferior de la pestaña MCP. Hacer scroll dentro del plugin
- No aparece la pestaña MCP → Verificar que el toggle "Enable MCP endpoint" está activo
- Versión diferente del plugin → Las opciones pueden estar en una pestaña "Settings" o "Config" dentro del plugin. Buscar toggles similares

---

## Elegir modo de color

Antes de importar, una decisión rápida.

Ya has visto que tu diseño tiene ambos modos: claro y oscuro (según la configuración de tu sistema operativo). Pero html.to.design solo importará **uno de los dos** a Figma.

ACTION: Usa AskUserQuestion:

Pregunta: ¿Con qué modo de color prefieres trabajar en Figma?
- Light mode (modo claro) — Recomendado, es el estándar para apps SaaS
- Dark mode (modo oscuro)

[Si elige dark mode]

ACTION: Modifica `PeopleOnBoard/outputs/html-propuestas/propuesta-final.html`: añade `class="dark"` al elemento `<html>` para que html.to.design importe el modo oscuro. Si ya tiene `class="light"`, cámbialo por `class="dark"`.

Listo, he configurado el modo oscuro como predeterminado para la importación.

[Si elige light mode]

ACTION: Modifica `PeopleOnBoard/outputs/html-propuestas/propuesta-final.html`: añade `class="light"` al elemento `<html>` para confirmar el modo claro como predeterminado.

---

## Importar tu diseño a Figma

Ahora viene el momento clave. Cierra el menú **"Import configurations"** en el plugin y vamos a enviar tu diseño directamente a Figma.

Antes de continuar, verifica:
- Tu archivo **PeopleOnBoard** está abierto en Figma
- El plugin **html.to.design** está ejecutándose con el MCP activado
- Has activado las opciones de **Import configuration** del paso anterior

Aquí va el prompt para usar en esta conversación (me puedes pedir que lo ejecute directamente):

```
Usa la herramienta import-html de html.to.design para enviar el diseño de PeopleOnBoard a Figma. Lee el archivo outputs/html-propuestas/propuesta-final.html y envía su contenido.
```

Cursor te pedirá permiso para usar la herramienta MCP — selecciona **"Allow"**. La importación puede tardar unos minutos, buen momento para prepararte un café o una infusión.

STOP: Introduce el prompt o dime que lo ejecute.

USER: [prompt o "ejecuta"]

---

ACTION: Lee `PeopleOnBoard/outputs/html-propuestas/propuesta-final.html` y usa la herramienta MCP `import-html` de html.to.design para enviar el contenido a Figma.

Si el MCP no está disponible o falla:
1. Verifica que el plugin está abierto en Figma y que el MCP está conectado
2. Si no funciona, guía al estudiante para importar manualmente: copiar el HTML → pegarlo en la pestaña "Code" del plugin dentro de Figma → Run

[Después de la importación]

¡Mira tu archivo de Figma!

STOP: ¿Ha aparecido el diseño en Figma?

USER: Sí / [Problema]

## [Si tiene problemas con la importación]

ACTION: Diagnosticar:
- No aparece nada → Verificar plugin activo, MCP conectado, reintentar
- Aparece incompleto → Puede ser un HTML muy largo. Intentar importar de nuevo o simplificar
- Error en la herramienta → Usar el fallback manual (pegar HTML en el plugin)

---

## Tu diseño en Figma

Ahí lo tienes. Tu diseño de PeopleOnBoard (generado por IA, dirigido por ti) ahora es un archivo de Figma completamente editable.

Explora un poco:
- **Panel de capas:** html.to.design ha traducido la estructura HTML en frames con **auto-layout** y capas con **nombres descriptivos** del HTML
- **Variables locales** (Local Variables): encontrarás variables de color, tipografía y espaciado creadas automáticamente
- **Componentes:** El plugin ha generado componentes con variantes para los estados hover y también para los iconos

También puede que notes algunas limitaciones, es normal con herramientas de importación:
- Los **nombres de las variables** puede que sean genéricos (basados en los valores, no en su función), en lugar de tokens semánticos
- Solo se ha importado **un modo de color** (el que elegiste). El otro modo está en el HTML si lo necesitas
- Algunos valores de espaciado puede que no sean exactos, el plugin puede capturar valores computados del navegador

Puedes hacer cambios manuales si quieres: mover elementos, ajustar colores, reorganizar. Figma es tu terreno.

Pero antes de que te pongas a editar a mano, te adelanto algo: en el **Sprint 2.2** vas a aprender a hacer cambios de diseño en Figma de una forma que te va a sorprender. Merece la pena esperar.

STOP: ¿Quieres explorar un poco el archivo o pasamos al cierre?

USER: [Respuesta]

## [Si quiere explorar]

Tómate tu tiempo. Cuando quieras, seguimos con el cierre.

STOP: ¿Seguimos?

USER: Sí / Adelante

---

## Cierre del sprint 2.1

Has completado el primer sub-sprint de la fase de diseño.

**Lo que has producido:**

| Archivo | Contenido |
|---------|-----------|
| `outputs/html-propuestas/` | 4 propuestas + propuesta-final.html |
| Archivo Figma **PeopleOnBoard** | Diseño importado y editable con variables |

**Lo que has aprendido:**

| Concepto | Para qué sirve |
|----------|----------------|
| Prompt → HTML | Convertir un briefing en propuestas visuales reales |
| Comparar opciones | Evaluar y elegir entre interpretaciones de un brief |
| html.to.design | Convertir HTML en diseños editables de Figma |
| MCP | Conectar herramientas de IA con aplicaciones externas |
| Import configuration | Activar opciones del plugin para importar variables, estilos y componentes |
| Variables en Figma | Variables de color, tipografía y espaciado importadas automáticamente (con naming genérico, el refinamiento viene después) |

**Filosofía reforzada:**
- HTML para validar rápido, Figma para diseñar con precisión
- Tú diriges las decisiones, la IA ejecuta el trabajo pesado
- El valor del PD está en los ajustes que solo un ojo entrenado puede hacer

---

STOP: Escribe `/sprint-2-2` cuando quieras continuar.

USER: /sprint-2-2

---

## Notas para Claude (No mostrar al estudiante)

### Sobre la generación de HTML
- Lee siempre `outputs/prompt-diseno.md` para generar las propuestas — no inventes un brief genérico
- Las 4 opciones deben ser **visualmente distintas**, no variaciones sutiles del mismo diseño
- Genera solo para el dispositivo indicado en el prompt del estudiante (mobile o desktop) — no ambos
- Cumple estrictamente todos los requisitos técnicos: base-8, variables CSS, accesibilidad, light+dark mode con `prefers-color-scheme` y soporte para clases en `<html>` que sobreescriban el media query
- Los archivos deben ser HTML completo y funcional, que se vean bien al abrir en navegador
- Avisa antes de crear cada archivo para que el estudiante apruebe el permiso en Cursor

### Sobre la elección y propuesta final
- Crea siempre `propuesta-final.html` — es el archivo que se importará a Figma
- Si elige una opción tal cual, copia su contenido como propuesta-final.html
- Si combina o modifica, genera propuesta-final.html con los cambios
- Propón eliminar las 4 opciones originales para mantener la carpeta limpia — si el estudiante prefiere conservarlas, respeta su decisión
- No presiones para iterar mucho en HTML — es mejor avanzar a Figma
- El objetivo es velocidad: elegir, confirmar y avanzar

### Sobre html.to.design y MCP
- La pestaña **Other** del plugin muestra la URL del servidor remoto — el estudiante copia esa URL y la pega en el chat
- Valida que la URL empiece por `https://h2d-mcp.divriots.com/` y termine en `/mcp` antes de generar el comando
- El comando para configurar el MCP es: `claude mcp add --transport http html-to-design "[URL]"`
- Para ejecutar el comando, el estudiante debe salir de Claude Code (`/exit`), ejecutarlo en la terminal, y volver con `claude --continue`
- Si el MCP no conecta: plugin no abierto en Figma, URL incorrecta, o MCP no añadido correctamente (verificar con `claude mcp list`)
- Si el MCP falla repetidamente, usa el **fallback manual**: copiar HTML → pegar en pestaña "Code" del plugin → Run
- Menciona las otras opciones (Cursor chat, Claude Desktop, Chrome extension) solo como referencia — el flujo principal es `claude mcp add` desde la terminal

### Sobre la importación a Figma
- Con la configuración recomendada activada, el plugin importa: auto-layout, variables y estilos locales, nombres de capa del HTML, componentes (hover e iconos), y hyperlinks
- Las **variables creadas** pueden tener naming genérico (basado en valores, no semántico). Es normal y se puede mejorar después
- El plugin puede crear **Text Styles y Color Styles** además de variables
- Solo se importa **un modo de color**. Las propuestas usan `prefers-color-scheme` (para preview en navegador), pero antes de importar se añade `class="light"` o `class="dark"` al `<html>` para forzar el modo elegido
- Antes de importar, pregunta al estudiante qué modo prefiere y ajusta la clase en el `<html>` de propuesta-final.html
- Lo que NO importa: un Design System completo (componentes maestros con todas sus variantes, documentación)
- Si la importación sale incompleta, puede ser un HTML demasiado extenso — intentar simplificar o dividir
- Si el estudiante quiere hacer cambios manuales en Figma, déjale — pero redirige suavemente hacia el Sprint 2.2
- No dramatices las limitaciones — menciónalas como posibilidades, no como hechos absolutos. El plugin puede mejorar con actualizaciones y el estudiante las verá por sí mismo

### Sobre Import configuration
- El botón "Import configuration" está en la pestaña MCP del plugin
- Si el estudiante no lo encuentra, puede estar en la parte inferior de la pestaña (hacer scroll)
- Si el plugin es una versión diferente, las opciones pueden estar en "Settings" o "Config"
- Si el estudiante importó sin activar las opciones, puede volver a importar después de activarlas
- "Use Autolayout" viene activado y bloqueado por defecto — no mencionarlo al estudiante
- "High-res images" es PRO (de pago) — no mencionarlo

### Sobre el ritmo
- Este sprint tiene muchos pasos pero debe sentirse ágil
- Los dos momentos WOW son: ver las propuestas HTML en navegador y ver el diseño en Figma
- No te extiendas en explicaciones teóricas — prioriza la acción
- Si el estudiante tiene preguntas sobre MCP o configuración, responde breve y sigue
- Conservar tokens: no animar al estudiante a hacer iteraciones extensas en HTML

## Criterios de Éxito

- [ ] Se han generado 4 propuestas HTML distintas en outputs/html-propuestas/
- [ ] Estudiante ha revisado las propuestas (navegador o Cursor)
- [ ] Estudiante ha elegido una dirección y existe propuesta-final.html confirmada
- [ ] Estudiante entiende el valor del HTML para validación rápida y el de Figma para diseño preciso
- [ ] Plugin html.to.design instalado en Figma
- [ ] MCP configurado con `claude mcp add` (o fallback manual)
- [ ] Estudiante ha elegido modo de color para Figma (light/dark) y se ha configurado en propuesta-final.html
- [ ] Diseño importado a Figma exitosamente
- [ ] Estudiante sabe que puede hacer cambios manuales pero que el Sprint 2.2 le enseñará algo mejor
