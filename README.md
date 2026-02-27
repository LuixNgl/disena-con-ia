# Diseña con IA

Curso práctico y gratuito para **Product Designers** que quieren integrar inteligencia artificial en su flujo de trabajo. Creado para diseñadores, no hace falta saber programar.

Aprende a sintetizar research, analizar competencia, crear briefings de diseño y generar propuestas visuales en Figma — todo dirigido por ti y ejecutado con IA.

> 🇬🇧 **Also available in English:** [github.com/LuixNgl/design-with-ai](https://github.com/LuixNgl/design-with-ai)
>
> El curso está gestionado por Claude, una IA que puede interactuar en cualquier idioma. La documentación y los materiales del curso, sin embargo, están disponibles en inglés o español.

---

## Qué aprenderás

| Sprint | Contenido | Duración |
|--------|-----------|----------|
| **1.1** | Bienvenida al proyecto | ~15 min |
| **1.2** | Síntesis de entrevistas de usuario con IA | ~15 min |
| **1.3** | Análisis de competencia desde la terminal | ~15 min |
| **1.4** | Crear un briefing de diseño profesional | ~20 min |
| **2.1** | Generar propuestas de diseño y llevarlas a Figma | ~30-40 min |
| **2.2** | Conectar Claude con Figma en tiempo real | ~40-50 min |
| **2.3** | Ecosistema de herramientas IA para diseño | ~20 min |

**Duración total:** ~3 horas

---

## Requisitos

- **Cuenta Claude Pro** (o superior) — [claude.ai](https://claude.ai) (unos 20€/mes)
- **Cursor** — [cursor.com](https://cursor.com) (gratuito)
- **Figma** — [figma.com](https://figma.com) (cuenta gratuita o de pago)
- **Espacio en disco:** Al menos 2 GB libres

---

## Instalación

Toda la instalación se hace en unos 15 minutos. Solo necesitas copiar y pegar unos comandos, no hace falta saber programar.

> **Si ya tienes alguno de estos pasos completados** (Cursor instalado, cuenta de Claude activa, etc.), ten en cuenta que no usaremos la app de Claude Desktop ni el chat de Cursor, sino el **terminal** de Cursor. Esto se explica en los pasos siguientes, así que mejor no saltarse ninguno y hacer la confirmación que se indica en cada paso.

### 1. Cuenta de Claude

Necesitas una cuenta **Claude Pro** (o superior) en [claude.ai](https://claude.ai). El plan Pro cuesta unos 20€/mes e incluye acceso a Claude Code, que es lo que usaremos en el curso.

**Recuerda:** No necesitas la app de Claude Desktop. Si la tienes instalada, no pasa nada, pero no la usaremos. El curso funciona desde la terminal de Cursor.

### 2. Descargar el curso

1. [**Descarga el curso (ZIP)**](https://github.com/LuixNgl/disena-con-ia/archive/refs/heads/main.zip)
2. Descomprime en una carpeta local (por ejemplo, en tu escritorio)

> **Importante:** Si mueves el curso a otra ubicación, mueve la **carpeta completa**. Contiene archivos ocultos necesarios para que funcione (la carpeta `.claude`). No arrastres archivos sueltos.

### 3. Instalar Cursor y abrir el proyecto

1. Descarga Cursor desde [cursor.com](https://cursor.com)
2. Instala siguiendo el asistente
3. Abre Cursor
4. Usa el botón **Open Project** o en el menú **File** → **Open Folder** → Selecciona la carpeta del curso que acabas de descomprimir

> En algunas versiones de Cursor verás **Open Project** en lugar de **Open Folder**.

### 4. Instalar Claude Code

Abre la terminal en Cursor: menú **View** → **Terminal** (o con el atajo `Cmd + J` en Mac / `Ctrl + J` en Windows). Se abrirá un panel en la parte inferior.

> **Importante:** Usaremos el **terminal** de Cursor durante todo el curso, no el chat de Cursor (panel derecho). Claude Code funciona en la terminal, puede conectarse con herramientas externas como Figma, ejecutar comandos personalizados (como los `/sprint` del curso), y usa tu suscripción de Claude sin necesitar la de Cursor.

Copia y pega este comando en la terminal y pulsa Enter:

**Mac / Linux:**
```
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**
```
irm https://claude.ai/install.ps1 | iex
```

**Si el comando anterior no funciona** (Mac, Linux y Windows), puedes instalar Claude Code con npm. Si no tienes npm instalado, primero instálalo desde el propio terminal de Cursor:

*Mac / Linux:*
```
curl -fsSL https://nodejs.org/install.sh | bash
```

*Windows:*
```
winget install -e --id OpenJS.NodeJS.LTS
```

> Si ves el error "winget: command not found", descarga Node.js manualmente desde [nodejs.org](https://nodejs.org) — pulsa el botón **LTS** y sigue el asistente con los valores por defecto.

Cuando termine, cierra Cursor completamente y ábrelo de nuevo. Después abre la terminal (**View** → **Terminal**) y continúa con el comando que viene a continuación.

Con npm instalado, ejecuta:
```
npm install -g @anthropic-ai/claude-code
```

Cuando termine, escribe `exit` para reiniciar la terminal y que reconozca el nuevo comando.

Para verificar que se ha instalado correctamente, escribe:

```
claude --version
```

Si ves un número de versión, todo está bien.

### 5. Conectar tu cuenta

Escribe `claude` en la terminal y pulsa Enter.

La primera vez te pedirá que conectes tu cuenta:

> Si no te pide que conectes tu cuenta y/o ves el mensaje **"credit balance too low"**, escribe `/login` en la terminal para conectar manualmente. Verifica que tu suscripción Claude Pro esté activa en [claude.ai/settings](https://claude.ai/settings).

1. Selecciona **"Claude account with subscription"**
2. Se abrirá una ventana del navegador para autenticarte — inicia sesión con tu cuenta de Claude
3. Vuelve a Cursor — verás que Claude Code está listo

Si te pregunta por preferencias de estilo de texto, elige la que prefieras pero intenta que se vea muy bien (no afecta al curso).

### 6. Empezar el curso

Ya está todo preparado. A partir de aquí, trabaja 100% desde la terminal de Cursor. Escribe:

```
/sprint-1-1
```

Y comienza la primera lección. Claude te guiará a partir de aquí.

---

## El proyecto

Trabajarás en **PeopleOnBoard**, una app de fichaje digital para PYMES españolas. Tu rol es Product Designer en una empresa ficticia llamada Louloudi Solutions, y tienes autonomía total sobre el diseño del producto.

### Carpetas

```
PeopleOnBoard/          → El proyecto en el que trabajarás
├── contexto-empresa/   → Información de la empresa y producto
├── entrevistas-usuario/→ Research con usuarios potenciales
└── outputs/            → Aquí guardarás tu trabajo

materiales/             → Templates y recursos reutilizables
```

---

## Ayuda

Si te pierdes o tienes dudas durante el curso, pregúntale a Claude directamente en la terminal de Cursor (donde se ejecuta el curso) — está ahí para ayudarte.

**Para retomar el curso donde lo dejaste**, escribe `claude --continue` en la terminal. Si necesitas elegir una conversación anterior concreta, escribe `claude` y luego `/resume`.

Última versión e instrucciones de instalación: [github.com/LuixNgl/disena-con-ia](https://github.com/LuixNgl/disena-con-ia)

---

## Créditos

Creado por [Luis Nagel](https://www.linkedin.com/in/luisnagel/)

### Agradecimientos

- Inspirado en la metodología de [Claude Code for Everyone](https://ccforeveryone.com) de [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/)
- Plugin [claude-talk-to-figma-mcp](https://github.com/arinspunk/claude-talk-to-figma-mcp) de [Xúlio Zé](https://www.linkedin.com/in/xulioze/) (adaptación para Claude) y [Sonny Lazuardi](https://www.linkedin.com/in/sonnylazuardi/) (proyecto original)

---

## Licencia

Este curso se distribuye bajo licencia [Creative Commons BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/).

Puedes compartirlo libremente bajo estas condiciones:
- **Atribución:** Cita al autor, Luis Nagel ([LinkedIn](https://www.linkedin.com/in/luisnagel/))
- **No comercial:** No se permite el uso comercial ni el lucro
- **Sin obras derivadas:** No se permite modificar, transformar ni crear obras derivadas

## Disclaimer

Este curso es un proyecto personal e independiente. No existe ninguna relación comercial, afiliación ni patrocinio con las empresas, herramientas o autores mencionados (Anthropic/Claude, Figma, Cursor, Carl Vellotti, ni cualquier otro). El autor no se responsabiliza del uso, disponibilidad ni cambios en las herramientas de terceros utilizadas.
