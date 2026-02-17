# Claude Talk to Figma — Guía de Instalación y Uso

## Qué es

Un plugin que permite a Claude modificar tus diseños de Figma en tiempo real mediante conversación. Es open source, gratuito, y funciona con Claude Code, Claude Desktop o cualquier herramienta compatible con MCP.

Creado por **Xúlio Zé** (adaptación para Claude) a partir del proyecto original de **Sonny Lazuardi**.

- Repositorio: [github.com/arinspunk/claude-talk-to-figma-mcp](https://github.com/arinspunk/claude-talk-to-figma-mcp)

---

## Requisitos

- **Figma Desktop** (no funciona desde la versión web de Figma)
- **Node.js** (necesario para npx — descárgalo desde [nodejs.org](https://nodejs.org/) si no lo tienes)
- **Espacio en disco:** ~500 MB libres (dependencias del plugin)
- **Claude Code**, **Claude Desktop** o cualquier herramienta compatible con MCP

---

## Primera vez: Instalación

### 1. Descargar el plugin y arrancar el servidor

Un solo comando descarga el plugin, instala las dependencias, construye el proyecto y arranca el servidor de conexión:

```bash
npx claude-talk-to-figma-mcp ~
```

El comando crea una subcarpeta `claude-talk-to-figma-mcp/` dentro de la ruta que indiques. Con `~`, el plugin queda en `~/claude-talk-to-figma-mcp/`. Puedes cambiar `~` por otra ruta si lo prefieres.

> **Recomendación:** Guarda el plugin en tu carpeta de inicio (`~/` en macOS/Linux, `%USERPROFILE%` en Windows). Evita rutas con espacios o carpetas sincronizadas con iCloud/OneDrive, ya que pueden causar problemas.

El servidor está listo cuando veas algo como:

```
[INFO] Status endpoint available at http://localhost:3055/status
[INFO] New client connected: client_...
```

**Deja esta terminal abierta** mientras trabajas con el plugin.

### 2. Importar el plugin en Figma

1. Abre **Figma Desktop** (no la versión web)
2. Abre o crea cualquier archivo de Figma Design (el menú de plugins solo aparece con un documento abierto)
3. Menú: **Plugins** → **Development** → **Import plugin from manifest...**
4. Navega hasta: `~/claude-talk-to-figma-mcp/src/claude_mcp_plugin/manifest.json`
5. Confirma que aparece "Claude MCP Plugin"

> **Nota:** Solo necesitas importarlo la primera vez. Después aparece directamente en el menú de plugins.

### 3. Configurar MCP en Claude Code

```bash
claude mcp add ClaudeTalkToFigma -- npx -p claude-talk-to-figma-mcp@latest claude-talk-to-figma-mcp-server
```

Si ya tienes una sesión de Claude Code abierta, sal con `/exit`, ejecuta el comando y vuelve con `claude --continue`.

Verifica que funciona: escribe `/mcp` en Claude Code y comprueba que **ClaudeTalkToFigma** aparece con check verde.

---

## Configurar en Claude Desktop

Si prefieres usar Claude Desktop en vez de Claude Code:

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

---

## Cada nueva sesión (3 pasos)

Cada vez que quieras usar Claude con Figma, necesitas estos tres pasos. El MCP ya está configurado de la instalación, eso no hay que repetirlo.

> **Importante:** El servidor socket se cierra cada vez que cierras la terminal donde lo ejecutaste. Es normal, hay que arrancarlo de nuevo cuando vuelvas.

### 1. Arrancar el servidor socket

Abre una terminal y ejecuta:

```bash
npx claude-talk-to-figma-mcp ~
```

Alternativa (si ya tienes el plugin descargado):

```bash
cd ~/claude-talk-to-figma-mcp && bun run socket
```

(En Windows: usa la ruta correspondiente, ej: `%USERPROFILE%\claude-talk-to-figma-mcp`)

Deja esta terminal abierta mientras trabajas.

### 2. Abrir el plugin en Figma

1. Abre tu archivo en Figma Desktop
2. Menú: clic derecho en el canvas → **Plugins** → **Claude MCP Plugin**
3. Pulsa **"Connect"** en el panel del plugin
4. Aparecerá un **código de canal** (ej: `v4f3uiqq`)

### 3. Conectar Claude al canal

Copia el código del plugin y dile a Claude:

```
Talk to Figma, channel v4f3uiqq
```

(Sustituye `v4f3uiqq` por tu código de canal)

**Importante:** Mantén el plugin abierto en Figma durante toda la sesión. Si se cierra o el canal cambia, comparte el nuevo canal con Claude.

---

## Qué puede hacer / Qué no puede

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

El plugin está en desarrollo activo. Estas capacidades se amplían con cada versión.

**Recomendación:** Para diseños completos desde cero, el enfoque HTML + html.to.design es más eficiente. Este plugin es ideal para iterar y refinar diseños existentes.

---

## Solución de problemas

### Error "npx: command not found"

Node.js no está instalado. Descárgalo e instálalo desde [nodejs.org](https://nodejs.org/) (versión LTS). Cierra y vuelve a abrir la terminal después de instalar.

### Error "Expected manifest.api to have type string"

Has seleccionado el manifest.json equivocado. El archivo correcto está en `src/claude_mcp_plugin/manifest.json` dentro de la carpeta del plugin (no el manifest.json de la raíz).

### El servidor socket no arranca

- Verifica que Node.js está instalado: `node --version`
- Verifica que el puerto 3055 está libre:
  - macOS: `lsof -i :3055`
  - Windows: `netstat -aon | findstr :3055`
- Si el puerto está ocupado, cierra el proceso que lo usa

### El plugin de Figma no conecta

- Verifica que el servidor socket está corriendo (la terminal donde ejecutaste npx debe estar abierta)
- Verifica que usas **Figma Desktop**, no la versión web
- Cierra y vuelve a abrir el plugin en Figma
- Reinicia el servidor socket

### El channel ID no funciona

- Reconecta el plugin en Figma (pulsa Disconnect y luego Connect)
- Copia el nuevo código de canal
- Compártelo de nuevo con Claude

### Una operación da timeout o error

- Simplifica la petición (pide cambios más pequeños)
- Verifica que el plugin sigue abierto en Figma
- Reconecta si es necesario

### El MCP no aparece en Claude Code

- Verifica con `claude mcp list`
- Si no aparece, vuelve a ejecutar el comando `claude mcp add`
- Si aparece en rojo, verifica que el servidor socket está corriendo

### Archivos del plugin desaparecen (macOS)

Si guardaste el plugin en una carpeta sincronizada con iCloud, macOS puede eliminar los archivos locales para ahorrar espacio. Solución:
- Clic derecho en la carpeta en Finder → "Download Now"
- O mejor: mueve el plugin a `~/` (fuera de iCloud)

---

## Prompt recomendado para diseño

El autor del plugin comparte un prompt para que Claude actúe como especialista UX/UI al trabajar con Figma. Puedes usarlo como base y adaptarlo añadiendo el contexto de tu producto, usuarios y objetivos:

[prompt-ux-ui-especialista-es.md](https://github.com/arinspunk/claude-talk-to-figma-mcp/blob/main/prompts/prompt-ux-ui-especialista-es.md)

---

## Créditos

- **Xúlio Zé** (adaptación para Claude): [github.com/arinspunk](https://github.com/arinspunk)
- **Sonny Lazuardi** (proyecto original): [github.com/sonnylazuardi](https://github.com/sonnylazuardi)
- Licencia MIT
