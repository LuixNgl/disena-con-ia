# Sprint 2.2: Claude habla con Figma

Este es un sprint clave en el que veremos una herramienta poco conocida y con mucho potencial.

Últimamente se habla mucho sobre si apps nuevas como Pencil.dev sustituirán a Figma. Antes de dejarnos llevar por el FOMO y migrar nuestros archivos a herramientas que todavía se están consolidando, es interesante conocer todo el potencial de Figma.

Lo que vas a conseguir: que yo (Claude Code) pueda hacer cambios en tu archivo de Figma en tiempo real, mientras hablamos.

Antes de empezar, quiero matizar las expectativas: el plugin que vamos a usar es un proyecto open source en desarrollo. Tiene limitaciones, pero lo que puede hacer ya es muy útil y, sobre todo, te va a abrir la cabeza a lo que viene.

¿Cuándo usar esto vs el enfoque HTML del sprint anterior? Para crear diseños completos desde cero, el flujo HTML sigue siendo más ágil. Este plugin brilla cuando ya tienes un diseño y quieres iterar sobre él sin salir de la conversación.

STOP: ¿Vamos a ello?

USER: Sí / Vamos / Adelante

---

## Instalación

Vamos a configurar todo paso a paso. La instalación consta de cuatro pasos, pero la parte técnica la hago yo. Tú solo tendrás que importar el plugin en Figma y ejecutar un comando.
Deberás dar permisos varias veces durante la instalación. Te recomiendo usar la opción 2 `always allow` para agilizarlo un poco.

STOP: ¿Comenzamos la instalación?

USER: Sí / Vamos / Adelante

---

### Paso 1: Descargar el plugin y arrancar el servidor

Voy a descargar y configurar el plugin por ti. Solo necesito saber dónde guardarlo.

ACTION: Usa AskUserQuestion para preguntar:

Pregunta: ¿Dónde quieres guardar el plugin?
- En tu carpeta de inicio (~/) (Recomendado)
- Dentro de la carpeta del proyecto

[Según la respuesta, usar esa ubicación como argumento del comando npx. Si elige inicio: `~`. Si elige proyecto: la ruta del proyecto. El comando npx creará automáticamente una subcarpeta `claude-talk-to-figma-mcp/` dentro de la ruta elegida.]

[**Importante — verificar la ruta elegida:**
- Si la ruta contiene **espacios** (ej: `Mobile Documents`, `My Documents`), avisar al estudiante: "Esa ruta tiene espacios, lo que puede causar problemas con el plugin. Te recomiendo usar la carpeta de inicio (`~/`) para evitar complicaciones."
- Si la ruta está dentro de **iCloud Drive** (macOS: `~/Library/Mobile Documents/com~apple~CloudDocs/...`), avisar: "Esa carpeta está sincronizada con iCloud. macOS puede eliminar los archivos locales para ahorrar espacio, lo que haría que el plugin deje de funcionar. Mejor guardarla en la carpeta de inicio (`~/`)."
- La carpeta de inicio (`~/`) evita ambos problemas y es la opción más fiable.]

Estoy descargando y configurando el plugin. Puede tardar unos segundos, no tienes que hacer nada.

ACTION: Ejecutar el siguiente comando en Bash con `run_in_background: true`:
`npx claude-talk-to-figma-mcp [RUTA_ELEGIDA]`

[Si npx pide confirmación de instalación, puede que necesite ejecutarse sin `run_in_background` la primera vez para aceptar el prompt, y luego rearrancar en background.]

ACTION: Comprobar periódicamente si el servidor está listo ejecutando:
`curl -s http://localhost:3055/status`
Repetir cada 5-10 segundos hasta que responda. Cuando el servidor responde, informar al estudiante.

[Si el servidor arranca correctamente]

Listo. El plugin está descargado y el servidor de conexión con Figma ya está funcionando.

STOP: ¿Continuamos?

USER: Sí / Continuamos / Adelante

## [Si tiene problemas con npx o el servidor]

ACTION: Diagnosticar:
- "npx: command not found" → Node.js no está instalado. Indicar al estudiante que lo descargue e instale desde [nodejs.org](https://nodejs.org/) (la versión LTS). Tras instalar, puede que necesite reiniciar la terminal (seguir el protocolo de "Recargar la Terminal" del agente instructor)
- Error de conexión → verificar internet
- Permiso denegado → verificar ruta, no necesita sudo/admin
- La carpeta ya existe → preguntar si quiere eliminarla y clonar de nuevo, o usar la existente
- El servidor no responde → Verificar con `curl -s http://localhost:3055/status`
- Puerto ocupado → macOS: `lsof -i :3055`. Windows: `netstat -aon | findstr :3055`. Matar el proceso que ocupa el puerto
- Timeout o proceso parado → Reintentar el comando npx. Si persiste, intentar manualmente: `cd [RUTA_ELEGIDA]/claude-talk-to-figma-mcp && npm install && npm run build && npm run socket`

---

### Paso 2: Importar el plugin en Figma

Ahora viene la parte de Figma. Este plugin no está en la tienda de Figma, por eso lo hemos descargado. Importarlo es sencillo:

1. Abre **Figma Desktop** (importante: la app de escritorio, no la web)
2. Abre o crea cualquier archivo de Figma Design (el menú de plugins solo aparece con un documento abierto)
3. Menú: **Plugins** → **Development** → **Import plugin from manifest...**
4. Navega hasta la carpeta del plugin y selecciona el archivo (ojo, fíjate bien en la ruta, no uses el primer `manifest.json` que encuentres):
   `[RUTA_ELEGIDA]/claude-talk-to-figma-mcp/src/claude_mcp_plugin/manifest.json`
5. Confirma que aparece **"Claude MCP Plugin"** en la lista de plugins de desarrollo

**Nota:** Figma guarda la ruta del plugin. Si mueves la carpeta más adelante, tendrás que volver a importarlo en Figma desde la nueva ubicación. Es fácil así que no le des vueltas.

STOP: ¿Ves "Claude MCP Plugin" en tus plugins de desarrollo?

USER: Sí / Lo veo / [Problema]

## [Si tiene problemas importando el plugin]

ACTION: Diagnosticar:
- No encuentra la opción "Import plugin from manifest..." → Verificar que es Figma Desktop (no web). En la app de escritorio: Plugins → Development → Import plugin from manifest...
- No encuentra el archivo manifest.json → La ruta correcta es `[RUTA_ELEGIDA]/claude-talk-to-figma-mcp/src/claude_mcp_plugin/manifest.json`. Ayudar a navegar
- Error "Expected manifest.api to have type string" → El estudiante ha seleccionado el manifest.json equivocado (probablemente el de la raíz del plugin en vez del de `src/claude_mcp_plugin/`). Indicar la ruta correcta
- Error al importar → Verificar que la descarga del Paso 1 se completó sin errores
- Usa Figma en el navegador → Necesita la app de escritorio para plugins de desarrollo. Puede descargarla desde figma.com/downloads

---

### Paso 3: Configurar MCP en Claude Code

Igual que configuramos html.to.design en el sprint anterior, ahora añadimos este servidor MCP.

Este es el comando:

```bash
claude mcp add ClaudeTalkToFigma -- npx -p claude-talk-to-figma-mcp@latest claude-talk-to-figma-mcp-server
```

---

Para ejecutarlo, el proceso es el mismo que con html.to.design:

1. Escribe `/exit` para cerrar esta sesión
2. En la terminal, ejecuta:

ACTION: Repite aquí el comando exacto listo para copiar y pegar:
`claude mcp add ClaudeTalkToFigma -- npx -p claude-talk-to-figma-mcp@latest claude-talk-to-figma-mcp-server`

3. Escribe `claude --continue` para retomar la conversación donde la dejamos

No te preocupes, no perderás nada. `claude --continue` retoma exactamente donde lo dejaste.

STOP: ¿Has ejecutado el comando y vuelto con `claude --continue`?

USER: Sí / Listo / Hecho / [Problema]

ACTION: Al salir con `/exit`, el servidor socket del Paso 1 se ha parado (es normal). Comprobar con `curl -s http://localhost:3055/status`. Si no responde, rearrancarlo en Bash con `run_in_background: true` ejecutando `cd [RUTA_ELEGIDA]/claude-talk-to-figma-mcp && bun run socket`. Esperar a que responda antes de continuar.

## [Si tiene problemas con el comando MCP]

ACTION: Diagnosticar:
- No reconoce `claude` → Verificar que Claude Code está instalado
- Quiere verificar → Ejecutar `claude mcp list` para ver los servidores configurados

---

Ahora vamos a verificar que la configuración MCP funciona. Escribe `/mcp` en el chat.

Deberías ver **ClaudeTalkToFigma** con un check verde y estado "connected".

Después de revisarlo, pulsa `Esc` para volver al chat y confirmar que lo has visto.

STOP: ¿Lo ves con check verde?

USER: Sí / Lo veo / [Problema]

## [Si el MCP no aparece o no está verde]

ACTION: Diagnosticar:
- No aparece en la lista → El comando `claude mcp add` no se ejecutó. Repetir Paso 3
- Aparece pero en rojo/failed → Puede ser que el servidor socket del Paso 1 no esté corriendo. Verificar con `curl -s http://localhost:3055/status`. Si no responde, rearrancar: ejecutar `npx claude-talk-to-figma-mcp [RUTA_ELEGIDA]` en Bash con `run_in_background: true` y esperar a que responda

---

### Paso 4: Conectar con Figma

Ahora abre tu archivo **PeopleOnBoard** en Figma (el que creaste en el Sprint 2.1).

Para ejecutar el plugin:
1. En Figma: **Plugins** → **Development** → **Claude MCP Plugin** → **Run**
2. Pulsa **"Connect"** en el panel del plugin si ese botón está activo (normalmente está conectado por defecto)
3. Aparecerá un **código de canal** (algo como `v4f3uiqq`)
4. Cópialo y pégamelo aquí

STOP: Pégame el código de canal.

USER: [channel ID]

---

### Paso 5: Establecer conexión

ACTION: Usa la herramienta `join_channel` del MCP ClaudeTalkToFigma con el channel ID que proporcionó el estudiante. Confirma la conexión exitosa.

[Si la conexión es exitosa]

Conectado. Ya puedo comunicarme con tu archivo de Figma.

Un par de cosas importantes antes de seguir:

**Permisos:** Para que la experiencia sea fluida, cuando Cursor te pida permiso para una herramienta de Figma, elige la opción **"2. Always allow"**. Así no tendrás que autorizar cada cambio.

**Control total:** Todo lo que haga en tu archivo de Figma puedes deshacerlo con `Cmd + Z` (macOS) o `Ctrl + Z` (Windows). Figma guarda el historial de versiones automáticamente. Tienes el control total, como si trabajaras con otro miembro de tu equipo.

**Mantén el plugin abierto:** Mientras trabajes con esta funcionalidad, el plugin tiene que estar abierto en Figma. Si se desconecta o cambia el canal, avísame, dame el nuevo canal y reconectamos.

STOP: ¿Continuamos?

USER: Sí / Continuamos / Adelante

## [Si la conexión falla]

ACTION: Diagnosticar:
- Channel ID incorrecto → Pedir que copie de nuevo el código del plugin
- Plugin no conectado → Verificar que el plugin está abierto, pulsó "Connect" en el plugin si hacía falta y que el socket server está corriendo
- Timeout → Verificar que el websocket sigue corriendo en background, reiniciar si es necesario
- Error de WebSocket → Verificar que el puerto 3055 está libre y accesible. Se le puede indicar que comparta el código completo que destaca el plugin in color verde. Tiene este formato: Connected to server on port 3055 in channel: skylapju

---

## Tu primera prueba

Vamos a hacer algo rápido para que veas cómo funciona. Voy a usar la función `get_document_info`

ACTION: Usa `get_document_info` para leer el archivo de Figma del estudiante. Muestra un resumen breve de lo que ves: páginas, frames principales, estructura general.

Ahora puedo ver tu archivo de Figma. Esto es lo que encuentro:

[Resumen de la estructura del documento: páginas, frames, elementos principales]

---

Hagamos tu primer cambio.

ACTION: Usa AskUserQuestion para preguntar:

Pregunta: ¿Qué quieres que cambie en tu diseño?
- Cambiar el color de un botón o elemento
- Cambiar un texto
- Ajustar el tamaño de un componente

[El estudiante puede elegir una opción o escribir su propia petición]

ACTION: Ejecuta el cambio solicitado usando las herramientas del MCP (set_fill_color, set_text_content, resize, etc. según corresponda).
Si el elemento tiene un degradado (gradient) y el estudiante pide cambiar su color, avisarle antes: "Ese elemento tiene un degradado. El plugin no puede manejar gradientes: al cambiar el color, lo reemplazará por un color plano. ¿Quieres que siga adelante o prefieres probar con otro elemento?"

Mira tu archivo de Figma: acabas de ver una agente de IA modificando tu diseño en tiempo real.

STOP: ¿Lo ves reflejado en Figma?

USER: Sí / Lo veo / [Problema]

## [Si el cambio no se refleja]

ACTION: Diagnosticar paso a paso:
1. ¿El plugin sigue abierto en Figma? → Si no, volver a abrir y reconectar
2. ¿El canal es el correcto? → Si cambió, pedir nuevo channel ID y reconectar con join_channel
3. ¿La herramienta devolvió error? → Leer el error y adaptar: puede ser un nodo incorrecto, un valor inválido, etc.
4. Intentar un cambio más simple (ej: cambiar un texto) para confirmar que la conexión funciona
5. Si nada funciona → Reiniciar: cerrar plugin en Figma, detener el servidor, volver a arrancarlo (ver Notas para Claude), reconectar

## [Si pide algo fuera de capacidades]

Esto es un buen momento para hablar de las limitaciones. Ese cambio en concreto no es posible todavía con el plugin, pero hay muchas cosas que sí puede hacer. Vamos a ver el panorama completo.

---

## Qué puede y qué no puede hacer

Aquí tienes una referencia rápida de las capacidades actuales del plugin:

| Lo que puede hacer | Lo que no puede (por ahora) |
|---|---|
| Cambiar colores de relleno y borde | Crear gradientes |
| Crear formas (rectángulos, elipses, texto, estrellas) | Crear paths vectoriales complejos |
| Modificar tipografía (fuente, tamaño, peso, interlineado) | Cambiar variantes de componentes |
| Aplicar y configurar auto-layout | Crear prototipos interactivos |
| Añadir sombras y efectos | Gestionar plugins de terceros |
| Leer y analizar la estructura del documento | Editar imágenes |
| Clonar, agrupar y reorganizar elementos | Exportar assets directamente |
| Usar componentes de la librería local | Crear animaciones |
| Redimensionar y mover elementos | Acceder a funciones PRO de Figma |

El plugin está en desarrollo activo. Estas capacidades se amplían con cada versión. Puedes consultar la información actualizada en https://github.com/arinspunk/claude-talk-to-figma-mcp

Y recuerda: para diseños completos desde cero, el enfoque HTML del Sprint 2.1 sigue siendo más eficiente. Este plugin es ideal para iterar y refinar.

**Un recurso extra:** El autor del plugin comparte un prompt para que Claude actúe como especialista UX/UI al trabajar con Figma. Es un buen punto de partida. Puedes usarlo tal cual o adaptarlo añadiendo el contexto de tu producto, usuarios y objetivos. Lo tienes aquí: [prompt-ux-ui-especialista-es.md](https://github.com/arinspunk/claude-talk-to-figma-mcp/blob/main/prompts/prompt-ux-ui-especialista-es.md)

Si quieres guardar alguno de estos recursos o comandos para consultarlos después, dime "anótalo en mis apuntes".

STOP: ¿Todo bien?

USER: Sí / Claro / Entendido / Alguna duda

---

## Tu turno

Ahora que ya sabes qué puede hacer, es buen momento para probar por tu cuenta. Pídeme 2 o 3 cambios en tu diseño: ajustar colores, mover elementos, cambiar tipografías, reorganizar algo... Piensa en ello como si estuvieras dirigiendo a un diseñador junior.

STOP: Cuando hayas terminado de probar, avísame para seguir.

USER: Listo / Seguimos / Adelante

ACTION: Ejecutar los cambios que el estudiante pida usando las herramientas MCP. Si pide algo fuera de capacidades, explicar la limitación y sugerir una alternativa. No limitar el número de cambios, dejar que explore. Cuando diga que quiere continuar, seguir con la siguiente sección.

---

## Cómo usar fuera del curso

Ahora que ya tienes todo configurado, quiero asegurarme de que puedes usar esto por tu cuenta cuando quieras.

### Reiniciar para futuras sesiones

Cada vez que quieras usar Claude con Figma, necesitas tres cosas:

1. **El servidor socket corriendo** → Abre una terminal → ejecuta `npx claude-talk-to-figma-mcp [RUTA_ELEGIDA]` (o desde la carpeta del plugin: `cd [RUTA_ELEGIDA]/claude-talk-to-figma-mcp && bun run socket`)
2. **El plugin abierto en Figma** → Plugins → Development → Claude MCP Plugin → Connect
3. **Conectar Claude al canal** → Copia el código del plugin y dile a Claude: `Talk to Figma, channel {tu-código}`

El MCP ya está configurado, eso no hay que repetirlo.

Y recuerda: el plugin tiene que estar abierto en Figma durante toda la sesión. Si se cierra o el canal cambia, comparte el nuevo canal.

STOP: ¿Queda claro?

USER: Sí / Claro / Entendido

---

### Desde la terminal del sistema

Si quieres usar esta funcionalidad fuera de Cursor, puedes hacerlo directamente desde la terminal de tu sistema operativo: **Terminal** en macOS o **PowerShell** en Windows:

1. En una pestaña: `npx claude-talk-to-figma-mcp [RUTA_ELEGIDA]`
2. En otra pestaña: escribe `claude` para abrir Claude Code
3. Dile a Claude: `Talk to Figma, channel {tu-código}`

---

### Desde Claude Desktop (opcional)

Si tienes la app **Claude Desktop** instalada, también puedes usar esta funcionalidad desde allí. Es otra forma válida y cómoda.

Necesitas una configuración previa (solo la primera vez):

1. Abre Claude Desktop → **Settings** → **Developer** → **Edit Config**
2. Añade esta configuración:

```json
{
  "mcpServers": {
    "ClaudeTalkToFigma": {
      "command": "npx",
      "args": ["-p", "claude-talk-to-figma-mcp@latest", "claude-talk-to-figma-mcp-server"]
    }
  }
}
```

Si ya tienes otros servidores MCP configurados, añade solo la entrada `"ClaudeTalkToFigma": { ... }` dentro de `"mcpServers"`, no reemplaces todo el archivo.

3. Reinicia Claude Desktop
4. Usa el modo **Chat** (que soporta herramientas MCP)

Después de esa configuración, cada nueva sesión es igual: socket server corriendo + plugin Figma abierto + compartir channel ID.

---

Hemos guardado todas estas instrucciones en `materiales/Guia_ClaudeTalkToFigma.md` para que puedas consultarlas cuando quieras.

ACTION: Confirmar que el archivo Guia_ClaudeTalkToFigma.md existe en materiales/. Si no existe, crearlo con el contenido de la guía (ver archivo de referencia).

STOP: ¿Alguna duda sobre cómo usarlo fuera del curso?

USER: No / Todo claro / Continuamos

---

## Cierre

### Reconocimiento al autor

Este plugin es obra de **Xúlio Zé**, un desarrollador gallego que adaptó el proyecto original de **Sonny Lazuardi** para que funcione con Claude. Es open source, gratuito, y puedes seguir su evolución en [github.com/arinspunk/claude-talk-to-figma-mcp](https://github.com/arinspunk/claude-talk-to-figma-mcp).

---

### Compartir en LinkedIn

Si te está resultando útil el curso, quizá puedes grabar lo que estás haciendo y compartirlo en LinkedIn. No olvides mencionar al autor, te lo agradecerá mucho, [Luis Nagel](https://www.linkedin.com/in/luisnagel/). Recuerda que este curso es gratuito, compartiendo le llegará a más gente y destacará tu perfil.

---

### Siguiente sprint

En el siguiente sprint cerraremos el curso haciendo un repaso por encima de otras opciones para trabajar con IA e incluye un bonus final de regalo. Si hay suficiente demanda, el curso podría ampliarse con sprints dedicados a otras funcionalidades.

---

### Resumen

**Lo que has conseguido:**

| Resultado | Descripción |
|-----------|-------------|
| Plugin instalado | Tu propio plugin de Figma conectado a Claude |
| MCP configurado | Claude Code puede comunicarse con Figma |
| Diseño modificado | Cambios reales en tu archivo PeopleOnBoard |
| Guía de referencia | `materiales/Guia_ClaudeTalkToFigma.md` para futuras sesiones |

**Lo que has aprendido:**

| Concepto | Para qué sirve |
|----------|----------------|
| MCP bidireccional | Claude lee y modifica Figma en tiempo real |
| Plugin local | Instalar herramientas no publicadas en la tienda de Figma |
| Capacidades y límites | Saber cuándo usar MCP vs enfoque HTML |
| Autonomía de uso | Saber reiniciar, usar desde terminal y Claude Desktop |

STOP: Escribe `/sprint-2-3` cuando quieras continuar con la guía de herramientas.

USER: /sprint-2-3

---

## Notas para Claude (No mostrar al estudiante)

### Sobre el Comando npx y el Servidor en Background
- Ejecutar `npx claude-talk-to-figma-mcp [RUTA]` con Bash `run_in_background: true`
- Este comando clona el repo, instala dependencias, construye y arranca el servidor websocket
- Verificar que el servidor está listo con `curl -s http://localhost:3055/status` — repetir cada 5-10 segundos hasta que responda
- **Ruta del plugin:** El comando npx crea una subcarpeta `claude-talk-to-figma-mcp/` dentro de la ruta elegida. Si el estudiante elige `~`, el plugin queda en `~/claude-talk-to-figma-mcp/`. Todas las rutas a archivos del plugin deben incluir esta subcarpeta
- Si npx pide confirmación interactiva para instalar el paquete, puede que necesite ejecutarse sin background primero. En ese caso, ejecutar normalmente, esperar a que complete, y si bloquea la terminal, matarlo y rearrancar con `cd [RUTA_ELEGIDA]/claude-talk-to-figma-mcp && bun run socket` en background
- **El servidor muere al hacer `/exit`:** Cuando el estudiante sale con `/exit` para ejecutar `claude mcp add` y vuelve con `claude --continue`, el servidor socket ya no está corriendo. Es imprescindible rearrancarlo antes de verificar `/mcp` o conectar con Figma
- Si el servidor se cae durante el sprint, rearrancarlo con: `cd [RUTA_ELEGIDA]/claude-talk-to-figma-mcp && bun run socket` en Bash con `run_in_background: true`

### Detección de SO
- El comando npx es cross-platform, no necesita adaptación por SO
- Sin embargo, sigue siendo necesario conocer el SO del estudiante para:
  - Atajos de teclado: `Cmd` (macOS) vs `Ctrl` (Windows)
  - Comandos de troubleshooting: `lsof -i :3055` (macOS) vs `netstat -aon | findstr :3055` (Windows)
- Si no se conoce el SO del estudiante desde un sprint anterior, detectarlo por contexto del sistema o preguntar solo si es necesario para troubleshooting

### Sobre el Puerto 3055
- Si el puerto 3055 está ocupado: macOS `lsof -i :3055`, Windows `netstat -aon | findstr :3055`
- El servidor arrancado en background morirá cuando se cierre la sesión de Claude Code — es normal
- Para futuras sesiones, el estudiante debe arrancarlo manualmente (explicado en la sección "Cómo usar fuera del curso" y en la guía)

### Sobre la Ubicación del Plugin
- Recomendar siempre `~/` (carpeta de inicio) como ubicación del plugin
- Rutas con **espacios** pueden causar fallos silenciosos
- **iCloud Drive** puede eliminar archivos locales para ahorrar espacio, rompiendo el plugin sin aviso. Si el estudiante ya lo tiene en iCloud y falla, sugerir: clic derecho en la carpeta → "Download Now" en Finder, o moverlo a `~/`

### Sobre Atajos de Teclado en Figma
- Algunos atajos de Figma cambian según la distribución del teclado. Ej: "Zoom to Fit" es `Cmd + 1` en teclado inglés pero `Shift + 1` en español
- Seguir la regla del CLAUDE.md: indicar siempre la ruta por menú como instrucción principal, atajos solo como referencia secundaria
- Si un atajo no funciona, preguntar al estudiante qué distribución de teclado usa

### Troubleshooting General
- Si `npx` no se encuentra → Node.js no está instalado. Instalar desde nodejs.org (versión LTS)
- Si la importación del plugin falla → verificar que es Figma Desktop (no web), ruta correcta al manifest.json
- Si el MCP no aparece tras `claude --continue` → verificar que el comando se ejecutó bien, probar `claude mcp list`
- Si el MCP aparece pero falla → verificar que el servidor socket está corriendo (`curl -s http://localhost:3055/status`)
- Si el socket server no arranca → verificar que puerto 3055 está libre
- Si archivos del plugin no existen → puede ser iCloud optimizando almacenamiento. Clic derecho en Finder → "Download Now"
- Si el plugin de Figma no conecta → verificar que el servidor socket está corriendo, puerto correcto
- Si el channel ID no funciona → reconectar plugin, copiar nuevo ID, intentar `join_channel` de nuevo
- Si una operación da timeout → simplificar la petición, reintentar

### Sobre las Herramientas de Figma
- No ejecutar acciones destructivas sin confirmación (aunque "Always allow" esté activado)
- Si el estudiante quiere seguir probando, dejarle un rato razonable y redirigir al cierre
- Si pide algo fuera de capacidades → explicar la limitación amablemente, sugerir alternativa manual o con enfoque HTML
- Herramientas clave disponibles: get_document_info, get_selection, set_fill_color, set_text_content, resize, move, clone, create_rectangle, create_text, create_ellipse, create_frame, set_auto_layout, set_corner_radius, set_stroke, set_effect, group_nodes, ungroup_nodes, get_styles, set_font_size, set_font_weight, set_line_height, set_letter_spacing, set_text_align, etc.

### Sobre el Ritmo
- La instalación es más rápida con la nueva versión, pero aún así mantener ritmo ágil con confirmaciones frecuentes
- El momento WOW es cuando Claude hace el primer cambio en Figma — no apresurarlo
- Si el estudiante quiere experimentar más en la sección de prueba, darle espacio
- No extender demasiado la sección de capacidades — la tabla es suficiente
- Las menciones a Luis Nagel siempre en tercera persona ("el creador del curso")

### Sobre la Guía de Materiales
- Verificar que `materiales/Guia_ClaudeTalkToFigma.md` existe
- Si no existe, crearla con las instrucciones de instalación y uso
- La guía es un recurso de referencia — no duplicar todo su contenido en el sprint

## Criterios de Éxito

- [ ] Plugin descargado e instalado via npx sin errores
- [ ] Plugin importado en Figma Desktop
- [ ] MCP configurado en Claude Code (`/mcp` muestra check verde)
- [ ] Socket server corriendo (verificado via status endpoint)
- [ ] Conexión establecida con channel ID
- [ ] Al menos un cambio visible en Figma ejecutado por Claude
- [ ] Estudiante comprende la tabla de capacidades/limitaciones
- [ ] Estudiante sabe reiniciar la funcionalidad (3 pasos)
- [ ] Estudiante conoce las opciones: terminal SO y Claude Desktop
- [ ] Guía referenciada en materiales/
- [ ] Créditos a Xúlio Zé y Sonny Lazuardi mencionados
- [ ] Invitación a compartir en LinkedIn (sin presionar)
