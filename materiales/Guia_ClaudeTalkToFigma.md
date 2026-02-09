# Claude Talk to Figma — Guía de Instalación y Uso

## Qué es

Un plugin que permite a Claude modificar tus diseños de Figma en tiempo real mediante conversación. Es open source, gratuito, y funciona con Claude Code, Claude Desktop o cualquier herramienta compatible con MCP.

Creado por **Xúlio Zé** (adaptación para Claude) a partir del proyecto original de **Sonny Lazuardi**.

- Repositorio: [github.com/arinspunk/claude-talk-to-figma-mcp](https://github.com/arinspunk/claude-talk-to-figma-mcp)

---

## Requisitos

- **Figma Desktop** (no funciona desde la versión web de Figma)
- **Bun** (se instala en el proceso, ocupa ~200 MB)
- **Espacio en disco:** ~500 MB libres (Bun + plugin + dependencias)
- **Claude Code**, **Claude Desktop** o cualquier herramienta compatible con MCP

---

## Primera vez: Instalación

### macOS / Linux

**1. Instalar Bun** (si no lo tienes):

```bash
curl -fsSL https://bun.sh/install | bash
```

Si la terminal no reconoce `bun` después de instalarlo, usa la ruta completa: `~/.bun/bin/bun`. Este problema es habitual con herramientas recién instaladas.

**2. Clonar el repositorio:**

```bash
git clone https://github.com/arinspunk/claude-talk-to-figma-mcp.git ~/claude-talk-to-figma-mcp
```

Puedes cambiar `~/claude-talk-to-figma-mcp` por la ruta que prefieras.

**3. Instalar dependencias y construir:**

```bash
cd ~/claude-talk-to-figma-mcp && bun install && bun run build
```

**4. Importar el plugin en Figma:**

1. Abre Figma Desktop
2. Menú: **Plugins** → **Development** → **Import plugin from manifest...**
3. Navega hasta: `~/claude-talk-to-figma-mcp/src/claude_mcp_plugin/manifest.json`
4. Confirma que aparece "Claude MCP Plugin"

**5. Configurar MCP en Claude Code:**

```bash
claude mcp add --transport stdio ClaudeTalkToFigma -- bun --cwd ~/claude-talk-to-figma-mcp run src/claude_mcp_server/index.ts
```

Si ya tienes una sesión de Claude Code abierta, sal con `/exit`, ejecuta el comando y vuelve con `claude --continue`.

---

### Windows

**1. Instalar Bun** (si no lo tienes):

Abre PowerShell como administrador:

```powershell
powershell -c "irm bun.sh/install.ps1 | iex"
```

Cierra y vuelve a abrir la terminal.

**2. Clonar el repositorio:**

```powershell
git clone https://github.com/arinspunk/claude-talk-to-figma-mcp.git %USERPROFILE%\claude-talk-to-figma-mcp
```

Puedes cambiar `%USERPROFILE%\claude-talk-to-figma-mcp` por la ruta que prefieras.

**3. Instalar dependencias y construir:**

```powershell
cd %USERPROFILE%\claude-talk-to-figma-mcp && bun install && bun run build:win
```

Nota: en Windows se usa `build:win` en vez de `build`.

**4. Importar el plugin en Figma:**

1. Abre Figma Desktop
2. Menú: **Plugins** → **Development** → **Import plugin from manifest...**
3. Navega hasta: `%USERPROFILE%\claude-talk-to-figma-mcp\src\claude_mcp_plugin\manifest.json`
4. Confirma que aparece "Claude MCP Plugin"

**5. Configurar MCP en Claude Code:**

```powershell
claude mcp add --transport stdio ClaudeTalkToFigma -- bun --cwd %USERPROFILE%\claude-talk-to-figma-mcp run src/claude_mcp_server/index.ts
```

Si ya tienes una sesión de Claude Code abierta, sal con `/exit`, ejecuta el comando y vuelve con `claude --continue`.

---

## Configurar en Claude Desktop

Si prefieres usar Claude Desktop en vez de Claude Code:

1. Abre Claude Desktop → **Settings** → **Developer** → **Edit Config**
2. Añade esta configuración:

**macOS / Linux:**

```json
{
  "mcpServers": {
    "ClaudeTalkToFigma": {
      "command": "bun",
      "args": ["--cwd", "/Users/TU_USUARIO/claude-talk-to-figma-mcp", "run", "src/claude_mcp_server/index.ts"]
    }
  }
}
```

**Windows:**

```json
{
  "mcpServers": {
    "ClaudeTalkToFigma": {
      "command": "bun",
      "args": ["--cwd", "C:\\Users\\TU_USUARIO\\claude-talk-to-figma-mcp", "run", "src/claude_mcp_server/index.ts"]
    }
  }
}
```

Sustituye `TU_USUARIO` por tu nombre de usuario. Si ya tienes otros servidores MCP configurados, añade solo la entrada `"ClaudeTalkToFigma": { ... }` dentro de `"mcpServers"`.

3. Reinicia Claude Desktop
4. Usa el modo **Chat** (que soporta herramientas MCP)

---

## Cada nueva sesión (3 pasos)

Cada vez que quieras usar Claude con Figma, necesitas estos tres pasos. El MCP ya está configurado de la instalación, eso no hay que repetirlo.

> **Importante:** El servidor socket se cierra cada vez que sales de Claude Code (`/exit`) o cierras la terminal. Es normal, hay que arrancarlo de nuevo cuando vuelvas.

### 1. Arrancar el servidor socket

Abre una terminal y ejecuta:

```bash
cd ~/claude-talk-to-figma-mcp && bun socket
```

(En Windows: usa la ruta correspondiente)

Si `bun` no se reconoce, usa la ruta completa: `~/.bun/bin/bun socket` (macOS) o `%USERPROFILE%\.bun\bin\bun.exe socket` (Windows).

Deja esta terminal abierta mientras trabajas.

### 2. Abrir el plugin en Figma

1. Abre tu archivo en Figma Desktop
2. Menú: clic derecho en el canvas → **Plugins** → **Claude MCP Plugin**

> **Nota:** Solo la primera vez necesitas importar el plugin desde el manifest.json. Las siguientes veces aparece directamente en el menú de plugins como cualquier otro plugin.

3. Pulsa **"Connect"** en el panel del plugin
4. Aparecerá un **código de canal** (ej: `v4f3uiqq`)

### 3. Conectar Claude al canal

Copia el código del plugin y dile a Claude:

```
Talk to Figma, channel v4f3uiqq
```

(Sustituye `v4f3uiqq` por tu código de canal)

**Importante:** Mantén el plugin abierto en Figma durante toda la sesión. Si se cierra o el canal cambia, comparte el nuevo canal con Claude.

El MCP ya está configurado — eso no hay que repetirlo.

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

### Error "bun: command not found"

Este es el error más frecuente. Ocurre cuando la terminal no reconoce Bun después de instalarlo.

**Solución rápida:** Usa la ruta completa en vez del nombre corto:
- macOS: `~/.bun/bin/bun` en vez de `bun`
- Windows: `%USERPROFILE%\.bun\bin\bun.exe` en vez de `bun`

**Para resolverlo de forma permanente:**
- macOS: ejecuta `exec $SHELL` para recargar la terminal
- Windows: cierra y vuelve a abrir la terminal o PowerShell
- Si nada funciona, cierra Cursor completamente y ábrelo de nuevo

### La ruta del servidor MCP no funciona

Si el comando `claude mcp add` da error o el MCP no conecta, puede ser un problema de ruta. Prueba con la ruta completa al archivo del servidor:

```bash
claude mcp add --transport stdio ClaudeTalkToFigma -- ~/.bun/bin/bun ~/claude-talk-to-figma-mcp/dist/talk_to_figma_mcp/server.js
```

En Windows:
```powershell
claude mcp add --transport stdio ClaudeTalkToFigma -- %USERPROFILE%\.bun\bin\bun.exe %USERPROFILE%\claude-talk-to-figma-mcp\dist\talk_to_figma_mcp\server.js
```

> **Nota:** Si la ruta `dist/talk_to_figma_mcp/server.js` no existe, prueba con `src/claude_mcp_server/index.ts`. La ruta varía según la versión del plugin.

### El servidor socket no arranca

- Verifica que Bun está instalado: `bun --version` (o `~/.bun/bin/bun --version`)
- Verifica que el puerto 3055 está libre:
  - macOS: `lsof -i :3055`
  - Windows: `netstat -aon | findstr :3055`
- Si el puerto está ocupado, cierra el proceso que lo usa

### El plugin de Figma no conecta

- Verifica que el servidor socket está corriendo (terminal abierta con `bun socket`)
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
- Verifica que Bun está accesible desde la terminal

---

## Prompt recomendado para diseño

El autor del plugin comparte un prompt para que Claude actúe como especialista UX/UI al trabajar con Figma. Puedes usarlo como base y adaptarlo añadiendo el contexto de tu producto, usuarios y objetivos:

[prompt-ux-ui-especialista-es.md](https://github.com/arinspunk/claude-talk-to-figma-mcp/blob/main/prompts/prompt-ux-ui-especialista-es.md)

---

## Créditos

- **Xúlio Zé** (adaptación para Claude): [github.com/arinspunk](https://github.com/arinspunk)
- **Sonny Lazuardi** (proyecto original): [github.com/sonnylazuardi](https://github.com/sonnylazuardi)
- Licencia MIT
