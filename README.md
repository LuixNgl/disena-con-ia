# Diseña con IA

Curso práctico y gratuito para **Product Designers** que quieren integrar inteligencia artificial en su flujo de trabajo. Sin experiencia técnica necesaria.

Aprende a sintetizar research, analizar competencia, crear briefings de diseño y generar propuestas visuales en Figma — todo dirigido por ti y ejecutado con IA.

---

## Qué Aprenderás

| Sprint | Contenido | Duración |
|--------|-----------|----------|
| **1.1** | Bienvenida al proyecto | ~15 min |
| **1.2** | Síntesis de entrevistas con IA | ~15 min |
| **1.3** | Análisis de competencia desde la terminal | ~15 min |
| **1.4** | Crear un briefing de diseño profesional | ~20 min |
| **2.1** | Generar propuestas de diseño y llevarlas a Figma | ~30-40 min |
| **2.2** | Conectar Claude con Figma en tiempo real | ~40-50 min |
| **2.3** | Ecosistema de herramientas IA para diseño | ~25-30 min |

**Duración total:** ~3 horas

---

## Requisitos

- **Cuenta Claude Pro** (o superior) — [claude.ai](https://claude.ai) ($20/mes)
- **Cursor** — [cursor.com](https://cursor.com) (gratuito)
- **Figma** — [figma.com](https://figma.com) (cuenta gratuita o de pago)

---

## Instalación

Toda la instalación se hace en unos 15 minutos. Solo necesitas copiar y pegar unos comandos — no hace falta saber programar.

### 1. Cuenta de Claude

Necesitas una cuenta **Claude Pro** (o superior) en [claude.ai](https://claude.ai). El plan Pro cuesta $20/mes e incluye acceso a Claude Code, que es lo que usaremos en el curso.

### 2. Instalar Cursor

1. Descarga Cursor desde [cursor.com](https://cursor.com)
2. Instala siguiendo el asistente

Cursor es un editor de código con IA integrada. Tiene un chat y un terminal — nosotros usaremos el **terminal**, que es la parte inferior de la pantalla. ¿Por qué el terminal y no el chat? Porque en el terminal funciona **Claude Code**, que puede conectarse con herramientas externas como Figma, ejecutar comandos personalizados (como los `/sprint` del curso), y funciona con tu suscripción de Claude sin necesitar la de Cursor.

### 3. Descargar el Curso

1. Descarga el archivo ZIP del curso desde este repositorio (botón **Code** → **Download ZIP**)
2. Descomprime en una carpeta local (por ejemplo, en tu escritorio)

### 4. Abrir el Proyecto

1. Abre Cursor
2. **File** → **Open Folder** → Selecciona la carpeta del curso que acabas de descomprimir

### 5. Instalar Claude Code

Abre el terminal en Cursor: menú **View** → **Terminal** (o con el atajo `Cmd + J` en Mac / `Ctrl + J` en Windows). Verás que se abre un panel en la parte inferior.

Copia y pega este comando en el terminal y pulsa Enter:

**Mac / Linux:**
```
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**
```
irm https://claude.ai/install.ps1 | iex
```

Espera a que termine la instalación. Después, cierra el terminal y ábrelo de nuevo (**View** → **Terminal**) para que reconozca el nuevo comando.

Para verificar que se ha instalado correctamente, escribe en el terminal:

```
claude --version
```

Si ves un número de versión, todo está bien.

### 6. Conectar tu Cuenta

Escribe `claude` en el terminal y pulsa Enter. La primera vez te pedirá que conectes tu cuenta:

1. Selecciona **"Claude account with subscription"**
2. Se abrirá una ventana del navegador para autenticarte — inicia sesión con tu cuenta de Claude
3. Vuelve a Cursor — verás que Claude Code está listo

Si te pregunta por preferencias de estilo de texto, elige la que prefieras (no afecta al curso).

### 7. Empezar el Curso

Ya está todo listo. En el terminal de Cursor, escribe:

```
/sprint-1-1
```

Y comienza la primera lección. Claude te guiará a partir de aquí.

---

## El Proyecto

Trabajarás en **PeopleOnBoard**, una app de fichaje digital para PYMES españolas. Tu rol es Product Designer en Louloudi Solutions, y tienes autonomía total sobre el diseño del producto.

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

Si te pierdes o tienes dudas durante el curso, pregúntale a Claude directamente — está ahí para ayudarte.

Si quieres retomar el curso donde lo dejaste, escribe `claude --continue` en el terminal.

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
