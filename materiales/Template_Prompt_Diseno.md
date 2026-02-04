# Template: Prompt Maestro de Diseño (The Ultimate Design Prompt)

Este documento es una plantilla reutilizable para generar prompts de diseño UI de alto nivel en cualquier proyecto. Úsala para estructurar tu pensamiento antes de pedirle nada a la IA.

> "El 80% del éxito de un diseño hecho por IA depende de la calidad del contexto que le das."

---

## 1. Definición del Proyecto (Tus Inputs)

*Rellena estas secciones con la información específica de tu reto actual.*

### Contexto y Problema
*¿Qué estamos construyendo y por qué? (Máx 2 frases)*
> [Escribe aquí...]

### Usuario Objetivo (Persona)
*¿Para quién es esto? ¿Qué les duele?*
> [Escribe aquí...]

### Insights de Research
*¿Qué aprendimos de las entrevistas y análisis de competencia?*
> [Resumen de síntesis de entrevistas...]
> [Resumen de análisis competitivo...]

### Alcance del MVP (Scope)
*¿Qué pantallas o flujos clave vamos a diseñar hoy? (Sé específico)*
1.  [Pantalla 1...]
2.  [Pantalla 2...]
3.  [Pantalla 3...]

### Dirección Artística (Vibe)
*¿Qué emociones debe transmitir? (Ej: Confianza, velocidad, calma, energía)*
*   **Estilo:** [Ej: Clean, Brutalist, Glassmorphism...]
*   **Color Base:** [Ej: Azul Índigo, Verde bosque...]
*   **Paleta secundaria:** [Colores de apoyo...]
*   **Referencias:** [Si tienes alguna web de inspiración]

---

## 2. Requisitos Técnicos para html.to.design

*Estos requisitos aseguran que el HTML generado se importe correctamente a Figma.*

### Especificaciones Obligatorias

1.  **Pixel Perfect:**
    *   Alineación precisa de todos los elementos
    *   Sin decimales en medidas (usar números enteros)
    *   Consistencia visual en todo el diseño

2.  **Dispositivo Único (sin responsive):**
    *   Diseña solo para el dispositivo elegido — no incluyas breakpoints para otros tamaños
    *   **Desktop:** Contenedor raíz de 1440px de ancho
    *   **Mobile:** Contenedor raíz de 390px de ancho (iPhone 14/15)
    *   El HTML debe tener un elemento raíz (`body` o contenedor principal) con el ancho fijo del dispositivo elegido

3.  **Sistema Base-8:**
    *   Todos los espaciados en múltiplos de 8: 8, 16, 24, 32, 40, 48, 56, 64px
    *   Márgenes, paddings, gaps siguiendo el sistema
    *   Tamaños de iconos: 16, 24, 32, 48px

4.  **Light + Dark Mode:**
    *   Incluye estilos para ambos modos (light y dark)
    *   Usa `prefers-color-scheme` para que ambos modos funcionen según la preferencia del sistema operativo (útil para previsualizar en navegador)
    *   También incluye soporte para clases en `<html>` (`html.light`, `html.dark`) que sobreescriben el media query cuando están presentes — esto permite controlar qué modo se importa a Figma
    *   Variables CSS para colores que cambien entre modos
    *   Contraste verificado en ambos modos

5.  **Accesibilidad (WCAG 2.1 AA + EN 301 549):**
    *   Ratio de contraste mínimo 4.5:1 para texto normal
    *   Ratio de contraste mínimo 3:1 para texto grande y elementos UI
    *   Áreas de toque mínimas de 44x44px
    *   Estados de foco visibles
    *   Jerarquía de encabezados correcta (h1, h2, h3...)

6.  **Variables CSS Tokenizadas:**
    *   Colores como variables: `--color-primary-500`, `--color-surface-bg`
    *   Espaciados como variables: `--space-xs`, `--space-sm`, `--space-md`
    *   Tipografía como variables: `--font-size-body`, `--font-weight-bold`
    *   Sombras como variables: `--shadow-sm`, `--shadow-md`

7.  **HTML Semántico:**
    *   Uso correcto de etiquetas: `<header>`, `<main>`, `<nav>`, `<section>`, `<article>`
    *   Botones como `<button>`, enlaces como `<a>`
    *   Formularios con `<label>` asociados a inputs
    *   Roles ARIA donde sea necesario

### Tipografía Recomendada
*   **Fuente principal:** Inter (disponible en Google Fonts y Figma)
*   **Tamaño base:** 16px para cuerpo de texto
*   **Escala tipográfica:** 12, 14, 16, 18, 20, 24, 32, 40, 48px

---

## 3. Instrucción para la IA (El Prompt)

*Cuando tengas rellena la parte superior, copia TODO este archivo (o la sección combinada) y pégalo en tu chat con la IA. Las reglas a continuación son tu "seguro de calidad".*

***

**ACTÚA COMO:** Product Designer Senior especializado en Design Systems y Accesibilidad.

**TU TAREA:**
Genera código HTML + CSS que represente el diseño de interfaz (UI) para las pantallas listadas en el **Alcance del MVP**. Este HTML será convertido a Figma usando el plugin html.to.design.

**REGLAS DE EJECUCIÓN (NO NEGOCIABLES):**

1.  **Output:**
    *   Genera archivos HTML con CSS embebido o en archivo separado
    *   El HTML debe ser válido, semántico y accesible
    *   Incluye todas las variables CSS definidas en la sección de requisitos técnicos

2.  **Sistema de Diseño Técnico (Pixel Perfect):**
    *   **Grilla Espacial:** Usa estrictamente un sistema **Base 8** (márgenes y paddings de 8, 16, 24, 32, 40, 48px...).
    *   **Tipografía:** Escala legible (16px como tamaño base para cuerpo de texto). Usa fuentes modernas sans-serif (Inter, Roboto, SF Pro).
    *   **Color:** Genera y utiliza **Variables CSS** semánticas (ej: `--color-primary-500`, `--color-surface-bg`, `--color-text-primary`) en lugar de valores hex "hardcoded".
    *   **Estructura:** Usa flexbox y grid para layouts. Nombra las clases de forma descriptiva.

3.  **Accesibilidad (A11y):**
    *   Cumple estrictamente con **WCAG 2.1 Nivel AA** y **EN 301 549**.
    *   Verifica ratios de contraste (mínimo 4.5:1 para texto normal).
    *   Áreas de toque mínimas de 44x44px.
    *   Estados de foco visibles y consistentes.

4.  **Variantes de Modo:**
    *   Incluye estilos para **Light Mode** (default) y **Dark Mode**.
    *   Usa `prefers-color-scheme` para alternar según la preferencia del sistema.
    *   También incluye soporte para clases en `<html>` (`html.light`, `html.dark`) que sobreescriben el media query cuando están presentes.

5.  **Estados Hover:**
    *   Incluye estados `:hover` en botones y elementos interactivos (enlaces, tarjetas clicables).
    *   Esto permite que html.to.design genere componentes con variantes hover en Figma automáticamente.

**CRITERIOS ESTÉTICOS (WOW FACTOR):**
*   Queremos un resultado visualmente impactante, nivel portfolio de Dribbble/Behance pero funcional.
*   Usa el espacio en blanco con generosidad.
*   Aplica sombras suaves y sutiles (elevation) para dar profundidad.
*   Evita el aspecto "wireframe" o "plantilla corporativa genérica". El diseño debe tener personalidad.

**OUTPUT ESPERADO:**
Genera 4 opciones de diseño con estilos diferentes pero todas cumpliendo los requisitos técnicos. Cada opción debe tener:
1. Archivo HTML completo y funcional
2. Nombre descriptivo del estilo (ej: "Minimalista Fresco", "Corporativo Moderno")
3. Breve descripción de las decisiones de diseño

---

## 4. Notas sobre html.to.design

### Qué hace el plugin (con la configuración recomendada)
- Convierte HTML/CSS a frames y layers de Figma
- Aplica **auto-layout** automáticamente (basado en flexbox/grid del HTML)
- Crea **variables y estilos de Figma** a partir de los valores del CSS (colores, tipografía, espaciados) — pero con naming genérico, no preserva los nombres de las variables CSS
- Reutiliza estilos locales existentes en el archivo de Figma (evita duplicados)
- Asigna **nombres de capa** descriptivos basados en las clases HTML
- Genera **componentes** con variantes hover (a partir de `:hover`) y para iconos
- Convierte enlaces `<a>` en elementos con **hyperlinks** en Figma

### Limitaciones conocidas del plugin
- Solo importa **un modo de color** (el que esté activo en el HTML) — por eso incluimos soporte para clases que sobreescriban el media query
- Los **nombres de variables** pueden ser genéricos (basados en valores, no semánticos)
- Algunos **valores importados** pueden ser computados (decimales, valores de layout)
- No crea un **Design System completo** (componentes maestros con todas sus variantes, documentación)
- No conecta instancias a componentes maestros

### Trabajo posterior en Figma
Después de importar con html.to.design, necesitarás:
1. Renombrar variables siguiendo una convención de tokens semánticos
2. Convertir elementos repetidos en **componentes** del Design System
3. Crear **variantes de componentes** adicionales (disabled, active, focus, etc.)
4. Limpiar valores computados (decimales, espaciados no estándar)
5. Organizar el Design System (páginas de componentes, documentación)
