# Sprint 1.2: Síntesis de entrevistas

Perfecto, vamos con el primer trabajo de verdad.

Este sprint dura unos **15 minutos** y al final tendrás tu primera síntesis de research.

Antes de diseñar nada, necesitamos entender para quién diseñamos.

STOP: ¿Vamos con ello?

USER: Sí

---

## ¿Qué es un IDE y por qué usamos Cursor?

Una pregunta que quizá te hagas: ¿por qué estamos en Cursor y no en ChatGPT o Claude.ai?

**ChatGPT / Claude.ai** son interfaces de chat en el navegador. Están bien para consultas puntuales, pero tienen una limitación importante: no pueden manejar tus archivos locales directamente.

**Cursor** es un **IDE** (Integrated Development Environment) — un entorno de desarrollo con IA integrada. Nos sirve para explorar carpetas, abrir archivos y previsualizarlos. Es la parte visual de nuestro entorno de trabajo.

La **terminal** (la parte de abajo, donde estás leyendo esto) es donde funciona **Claude Code** por **CLI** (Command Line Interface) para dar instrucciones al ordenador escribiendo texto. Aquí es donde hablamos tú y yo.

Cursor tiene su propio chat con IA (a la derecha), pero nosotros usamos Claude Code en la terminal porque es más potente: puede conectarse con herramientas como **Figma** (lo veremos en el Sprint 2), funciona con tu suscripción de Claude sin necesitar la de Cursor, y permite comandos personalizados como los `/sprint` que estamos usando.

STOP: ¿Te queda clara la diferencia?

USER: Sí / Entendido / Adelante

---

## Crear tu carpeta de trabajo

Vamos a probar cómo puedo gestionar archivos por ti.

Necesitamos una carpeta `outputs/` dentro de `PeopleOnBoard/` donde guardaremos todo lo que produzcas durante el curso. Pídeme que la cree, puedes usar algo como:

```
Crea la carpeta outputs dentro de PeopleOnBoard
```

**Importante:** Cursor me pedirá permiso para crear la carpeta. Usa una de estas dos opciones:
1. **Allow** — Autoriza esta acción
2. **Always allow** — Autoriza y no vuelve a preguntar para acciones similares

Si eliges la segunda, trabajaremos más fluido el resto del curso.

STOP: Pídeme crear la carpeta y autoriza el permiso.

USER: Crea la carpeta outputs dentro de PeopleOnBoard

---

ACTION: Crea la carpeta `PeopleOnBoard/outputs/` si no existe

¡Perfecto! Ya tienes tu espacio de trabajo preparado.

---

## Analizar las entrevistas

Tu equipo ha hecho tres entrevistas con usuarios potenciales de PeopleOnBoard:

- **Carmen López** — Directora de RRHH (la que compra y administra)
- **Laura Martínez** — Team Lead (la que aprueba solicitudes)
- **David García** — Developer (usuario final del día a día)

Tienen necesidades diferentes, y algunas incluso contradictorias. Eso es normal en research, parte de tu trabajo es identificar esos conflictos.

En la carpeta `materiales/` tienes una **template** (plantilla con la estructura ya definida) para sintetizar entrevistas. Así el resultado sale consistente y profesional sin tener que explicar el formato cada vez. Cuanto más específico seas, mejor resultado obtendrás. Esto aplica a cualquier IA, no solo aquí

Para pedirme que haga el análisis, fíjate en el prompt que vamos a usar:

```
Lee las entrevistas en PeopleOnBoard/entrevistas-usuario/ y genera una síntesis siguiendo la template materiales/Template_Sintesis_Entrevistas.md. Guárdala en PeopleOnBoard/outputs/sintesis-entrevistas.md
```

**Nota:** Verás que proceso bastante texto en la terminal. No necesitas leerlo todo aquí, al final te pediré permiso para crear el archivo. Igual que antes, elige **1. Allow** o **2. Always allow**.

STOP: Pídeme el análisis cuando quieras.

USER: Lee las entrevistas en PeopleOnBoard/entrevistas-usuario/ y genera una síntesis siguiendo la template materiales/Template_Sintesis_Entrevistas.md. Guárdala en PeopleOnBoard/outputs/sintesis-entrevistas.md

---

ACTION: Lee los tres archivos de entrevista en `PeopleOnBoard/entrevistas-usuario/` y genera una síntesis usando el template `materiales/Template_Sintesis_Entrevistas.md`. Guárdala en `PeopleOnBoard/outputs/sintesis-entrevistas.md`

[Después de crear el archivo]

¡Listo! He creado el archivo en tu carpeta de outputs.

Ábrelo desde el explorador de la izquierda: `PeopleOnBoard/outputs/sintesis-entrevistas.md`. También puedes hacer `Cmd + clic` (Mac) / `Ctrl + clic` (Windows) en la ruta para abrirlo directamente.

---

## Dar contexto con @

Un truco útil: cuando quieras que trabaje con un archivo concreto, puedes referenciarlo en tu mensaje con `@` seguido del nombre.

1. Escribe `@` en el input
2. Empieza a escribir el nombre del archivo
3. Cursor te mostrará sugerencias, selecciona con las flechas y tabulador

Por ejemplo, más adelante podrás escribir algo como "Resume los puntos clave de @sintesis-entrevistas.md" y yo tendré acceso directo al archivo. Lo usaremos en los próximos sprints.

STOP: ¿Queda claro?

USER: Sí / Entendido / Adelante

---

## Ver el archivo con formato

El archivo que ves es **Markdown** (`.md`) — un formato de texto que usa símbolos para dar formato (`#` para títulos, `**texto**` para negrita, `-` para listas). Es el estándar en documentación técnica.

Ahora mismo lo ves en texto plano, pero puedes verlo renderizado:

1. Haz clic en el archivo en el explorador para abrirlo (si no lo tienes abierto ya)
2. **Haz clic derecho** en la pestaña del archivo (arriba) y selecciona **"Open Preview"**
3. Se abrirá una vista previa con el formato aplicado, mucho más fácil de leer

También puedes usar el atajo `Cmd + Shift + V` (Mac) o `Ctrl + Shift + V` (Windows) para abrir la preview directamente.

Cuando termines de revisarlo, vuelve abajo a la terminal (si la cerraste, usa `Cmd + J` (Mac) / `Ctrl + J` (Windows)) para continuar.

STOP: ¿Puedes abrir la preview del archivo?

USER: Listo / Ya la veo / Hecho

---

## Los hallazgos

¿Has visto lo que has conseguido? Piensa en cuánto te habría llevado hacer esto manualmente: leer cada entrevista, tomar notas, organizarlas, redactar el documento...

Esto es exactamente lo que hace potente trabajar con IA a través de un IDE como Cursor. Tú decides qué analizar y cómo estructurarlo, y la IA ejecuta el trabajo pesado.

Ahora repasemos lo que encontramos.

**Lo que los tres usuarios tienen en común:**
1. **Odian la complejidad** — No quieren "software enterprise" con mil opciones
2. **Desktop es el punto de partida** — Empiezan la jornada abriendo el portátil, no tienen móvil de empresa
3. **Velocidad es clave** — Fichar debe ser instantáneo, no una tarea más

**Conflictos que tendremos que resolver:**
- **Light vs Dark mode:** Carmen prefiere claridad para leer bien, David prefiere modo oscuro
- **Eficiencia vs cultura:** David quiere fichar en 2 segundos, Carmen quiere que también conecte con la empresa
- **Profundidad:** Laura necesita aprobar y ver resúmenes, los demás solo quieren fichar

Estos conflictos no son problemas, son información valiosa para tomar decisiones de diseño. En el próximo sprint veremos qué hace la competencia, y eso nos ayudará a decidir qué camino tomar.

STOP: ¿Alguna duda sobre los hallazgos? Puedes hacerme preguntas sobre las entrevistas, como "¿cuál es el rol de Laura?" o "¿qué frustraciones tienen en común los tres?"

USER: Todo claro / Continuamos / No

---

## Cierre del sprint 1.2

Un tip antes de cerrar: si durante el curso ves algo que quieres recordar (un comando, un concepto, una idea) puedes decirme "anota esto en mis apuntes" y lo guardaré en `outputs/apuntes.md`. Así no tienes que salir de aquí para tomar notas.

¡Genial! Ya tienes tu primera síntesis de research.

**Lo que has aprendido:**
- La diferencia entre IDE (Cursor) y chat web (Claude.ai)
- Cómo pedirme que cree archivos y gestione permisos
- Cómo referenciar archivos con `@` para dar contexto en tus prompts
- Cómo previsualizar Markdown en Cursor
- Qué son las templates y cómo usarlas para estructurar resultados
- Cómo sintetizar varios documentos en uno solo

**Lo que has producido:**
- `outputs/sintesis-entrevistas.md` — Tu síntesis de investigación

En el **Sprint 1.3** vamos a analizar la competencia: qué ofrecen Factorial y Sesame HR, y cómo PeopleOnBoard puede diferenciarse.

STOP: Escribe `/sprint-1-3` cuando quieras continuar.

USER: /sprint-1-3

---

## Notas para Claude (No mostrar al estudiante)

### Sobre la carpeta outputs/
- Si la carpeta ya existe, no la vuelvas a crear ni comentes al respecto
- Si hay archivos previos en outputs/, no los menciones a menos que el estudiante pregunte

### Sobre las referencias con @
- La @ se enseña como forma de dar contexto en prompts, NO para abrir archivos
- Si el estudiante tiene problemas con @, ofrece alternativas: ruta completa o arrastrar archivo al input
- No insistas demasiado si prefiere otro método

### Sobre la síntesis
- Al crear la síntesis, SÍ identifica conflictos reales entre las personas (light vs dark, eficiencia vs cultura)
- No inventes datos que no estén en las entrevistas
- Destaca especialmente las necesidades relacionadas con fichaje (el MVP)

### Sobre Markdown preview
- Si el estudiante usa Windows, recuérdale que es Ctrl en lugar de Cmd
- Si tiene problemas abriendo la preview, puede usar la opción del menú: View → Command Palette → "Markdown: Open Preview"

## Criterios de Éxito

- [ ] Estudiante entiende la diferencia IDE vs chat web
- [ ] Estudiante entiende @ como forma de dar contexto en prompts
- [ ] Estudiante entiende qué son las templates y por qué las usamos
- [ ] Se ha creado `outputs/sintesis-entrevistas.md` con contenido correcto
- [ ] Estudiante sabe cómo previsualizar Markdown
- [ ] Estudiante conoce los conflictos principales entre usuarios
