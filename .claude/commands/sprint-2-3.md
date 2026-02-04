# Sprint 2.3: Cierre — Herramientas y Siguientes Pasos

Este es el último sprint del curso. No vamos a profundizar en nuevas herramientas, sino mostrar una visión de lo que existe y puedes explorar por tu cuenta. Y recuerda: estoy aquí, así que puedes preguntarme sobre cualquiera de ellas.

Antes de empezar, una reflexión importante.

A lo largo del curso hemos usado varias herramientas: Claude Code, html.to.design, claude-talk-to-figma. Mañana habrá versiones nuevas, herramientas nuevas, y titulares que digan que todo lo que sabes ha quedado obsoleto. Es normal — pasa cada semana.

Pero lo que has desarrollado aquí no caduca: la capacidad de definir un scope, sintetizar research, analizar competencia, dirigir la IA con criterio y llevar propuestas a Figma. Eso es tuyo. Las herramientas cambian — tu criterio como Product Designer es lo que les da valor.

STOP: ¿Vemos qué otras opciones de IA hay para un Product Designer?

USER: Sí / Empecemos / Adelante

---

## Agentes como Copiloto de Diseño

Puede que hayas oído hablar de "agentes de navegador" — IAs que abren un navegador real y usan herramientas como un humano, haciendo clic y navegando pantallas. Suena espectacular, pero en la práctica son lentos y poco dinámicos para tareas de diseño. Para cambios puntuales en Figma, los plugins como los que hemos usado son más eficientes y fiables.

Donde sí brilla el concepto de agente es en otra cosa: **tu propio copiloto de producto**.

Este curso que estás haciendo ahora mismo está gestionado por un agente (yo). Claude tiene unas instrucciones (un archivo CLAUDE.md y scripts de cada sprint) que le dicen cómo enseñarte, en qué orden, y qué hacer en cada situación. No es magia — es configuración.

Ahora imagina lo mismo aplicado a tu trabajo diario como Product Designer:
- Un agente que conoce tu producto, tus usuarios y tus objetivos
- Que analiza inputs (entrevistas, métricas, feedback) con el contexto de tu proyecto
- Que prepara entrevistas de usuario, define scopes, redacta comunicaciones a stakeholders
- Que hace análisis heurísticos de tu diseño o genera prompts para otras IAs con contexto específico

En tiempos de la IA, nuestro papel puede evolucionar hacia algo muy potente: **dirigir agentes con criterio de diseño**.

Si te interesa profundizar, Carl Vellotti tiene varios recursos excelentes:
- [Full Stack PM](https://fullstackpm.com/) — Cómo integrar IA en la gestión de producto para PMs
- [Claude Code for Everyone](https://ccforeveryone.com/) — Orientado a otros perfiles de producto

STOP: ¿Continuamos?

USER: Sí / Continuamos / Adelante

---

## Dentro de Figma: Imágenes, Make y Sites

Figma tiene varias funcionalidades de IA más allá de lo que hemos usado. Un repaso rápido:

### Imágenes con IA

Claude Code no genera imágenes — está centrado en texto y código. Pero Figma ya incluye funcionalidades de IA para **ampliar imágenes**, **quitar fondos** y **eliminar objetos**. También puedes usar herramientas más potentes como Photoshop, Affinity, IAs generativas como ChatGPT (con DALL-E), Gemini o Midjourney.

### Figma Make

Figma Make permite crear diseños completos o dar vida a elementos con interacciones multi-pantalla, todo desde prompts de texto (y ya hemos visto que tu agente copiloto de diseño es perfecto para crear esos prompts). Es especialmente interesante para prototipos rápidos.

Un detalle importante: los componentes que genera Make solo se editan por chat (no puedes modificarlos directamente como diseño). Pero hay un truco: puedes **copiar las pantallas generadas y pegarlas como diseño editable normal**, incluso dentro de Figma Sites.

### Figma Sites

Figma Sites permite publicar webs conectadas a tu dominio (o con un dominio de Figma). Incluye un **CMS integrado** (una base de datos para contenido dinámico) para que no dependas de otras como Supabase, Airtable o Firebase.

¿Para qué usarlo? Portfolio, tests de usuario con diseños reales, explicar funcionalidades a tu equipo, o incluso un entregable funcional.

### Resumen

| Herramienta | Para qué |
|---|---|
| Imágenes IA en Figma | Ampliar, quitar fondos, eliminar objetos |
| Figma Make | Prototipos interactivos desde prompts |
| Figma Sites | Publicar webs vivas con CMS |

STOP: ¿Vamos con lo siguiente?

USER: Sí / Vamos / Adelante

---

## Claude Code Más Allá del Diseño

Ya has visto que Claude Code genera HTMLs completos — pero puede ir bastante más lejos:

- **Sites más complejos:** Páginas con múltiples vistas, formularios funcionales, integraciones con APIs
- **Storybook:** Trasladar tu Design System a la web con componentes React documentados e interactivos — tu equipo de desarrollo puede consultarlos online
- **GitHub:** Subir todo a un repositorio (tu site o DS) para que cualquier miembro del equipo lo use, con control de versiones

No vamos a profundizar ahora, pero si alguna de estas opciones te interesa, pregúntame y te guío paso a paso.

STOP: ¿Seguimos?

USER: Sí / Seguimos / Adelante

---

## Explora Más

Aquí tienes algunas herramientas que merece la pena investigar por tu cuenta:

- **[Pencil.dev](https://pencil.dev)** — Diseño de interfaces con IA
- **[MagicPatterns](https://magicpatterns.com)** — Generación de componentes y layouts
- **[FlutterFlow](https://flutterflow.io)** — Apps no-code con interfaz visual
- **[Manus](https://manus.im)** — IA centrada en producto
- **Otros IDEs** — VS Code, Windsurf, Google Antigravity... el ecosistema crece cada semana
- **Notion + Figma Make** — Prototipar PRDs automáticamente ([ver vídeo](https://www.youtube.com/watch?v=Pbe7rC2fMJg&list=PLMs9KUTRYQvDjTZxB8kvHDU5eMY2GNaTX&index=20))

No hace falta que las pruebes todas. Lo importante es saber que existen y tener criterio para elegir cuál encaja en tu flujo de trabajo.

STOP: ¿Continuamos con el cierre del curso?

USER: Sí / Continuamos / Vamos

---

## Tu Diploma

Claude Code no genera imágenes, pero sí puede crear un prompt para una IA que lo haga. Vamos a preparar un diploma personalizado del curso.

ACTION: Usa AskUserQuestion para preguntar:

Pregunta: ¿Cómo quieres que aparezca tu nombre en el diploma?
- [Campo de texto libre]

[Nota: usar un AskUserQuestion con una sola opción de texto libre. Si AskUserQuestion no permite texto libre, simplemente preguntar con un STOP:]

STOP: ¿Cómo quieres que aparezca tu nombre en el diploma? Escríbelo tal como quieres que se vea.

USER: [Nombre completo del estudiante]

---

Perfecto. Aquí tienes un prompt que puedes usar en cualquier IA que genere imágenes — ChatGPT, Gemini, Midjourney, o la que prefieras:

ACTION: Genera y muestra el siguiente prompt adaptado con el nombre del estudiante:

```
Crea un diploma digital moderno y minimalista con las siguientes características:

- Título: "Diseña con IA"
- Subtítulo: "Curso de diseño de producto con inteligencia artificial"
- Completado por: [NOMBRE DEL ESTUDIANTE]
- Autor del curso: Luis Nagel
- Estilo: limpio, profesional, fondo claro con acentos sutiles de color
- Elementos gráficos: referencias sutiles a herramientas de diseño e IA (nodos conectados, formas geométricas, o iconografía abstracta que evoque Figma, Claude y Cursor)
- Formato: horizontal (landscape), 1920x1080px
- Tipografía: moderna, sans-serif, con jerarquía clara
- Debe verse bien compartido en LinkedIn y redes sociales
- No incluir logos de empresas — solo elementos gráficos abstractos que evoquen las herramientas
```

Copia este prompt y pégalo en ChatGPT, Gemini o la IA de imágenes que prefieras. En unos segundos tendrás tu diploma.

---

Y si quieres compartirlo en LinkedIn, aquí tienes un mensaje sugerido:

ACTION: Genera y muestra el siguiente mensaje adaptado con el nombre del estudiante:

```
He completado el curso "Diseña con IA" de Luis Nagel — un curso práctico donde he aprendido a integrar herramientas de inteligencia artificial en mi flujo de trabajo como Product Designer.

Desde sintetizar research con IA hasta generar propuestas de diseño y conectar Claude con Figma en tiempo real. El curso es gratuito y está creado para diseñadores sin experiencia técnica.

#DiseñoConIA #ProductDesign #IA #Figma #ClaudeCode
```

Etiqueta a [Luis Nagel](https://www.linkedin.com/in/luisnagel/) en la publicación para que le llegue.

STOP: Tómate un momento para crear tu diploma si quieres. Cuando estés listo, seguimos con el cierre.

USER: Listo / Seguimos / Adelante

---

## Lo que Has Conseguido

Hagamos un repaso rápido de todo lo que has logrado en este curso:

| Sprint | Lo que has conseguido |
|--------|----------------------|
| 1.1 | Configurar tu entorno de trabajo con IA |
| 1.2 | Sintetizar research con IA en segundos |
| 1.3 | Analizar competencia desde la terminal |
| 1.4 | Crear un briefing de diseño profesional |
| 2.1 | Generar propuestas de diseño y llevarlas a Figma |
| 2.2 | Conectar Claude con Figma en tiempo real |
| 2.3 | Conocer el ecosistema de herramientas IA para diseño |

Todo esto, dirigido por ti y ejecutado con IA. Ese es el modelo.

Y un apunte: PeopleOnBoard responde a una necesidad legal real que afecta a miles de PYMES. Lo que has construido aquí — research, análisis, briefing, diseño en Figma — es una base sólida para un producto real. Si te animas a seguir desarrollándolo, ya tienes más ventaja que la mayoría.

---

## Tus Materiales

En tu carpeta tienes todo lo que hemos creado durante el curso, listo para reutilizar en tus proyectos:

- **Templates** en `materiales/`:
  - Síntesis de entrevistas
  - Análisis de competencia
  - Prompt de diseño
  - Guía de Claude Talk to Figma
- **Los outputs de PeopleOnBoard** en `PeopleOnBoard/outputs/` como referencia de lo que puedes producir
- **Tus apuntes** (si los has creado durante el curso)

Todo esto es tuyo — úsalo, adáptalo, compártelo.

---

## Despedida

Espero que hayas disfrutado del curso y que las habilidades que has desarrollado te ayuden en tu día a día como Product Designer. El objetivo era que salieras de aquí con herramientas prácticas y, sobre todo, con la confianza de que puedes integrar la IA en tu flujo de trabajo.

Este curso es un proyecto personal y gratuito de Luis Nagel, creado para la comunidad de diseño. No tiene afiliación, relación comercial ni financiación de ninguna de las empresas o herramientas mencionadas, ni de los autores citados.

El autor agradecería mucho si le mandas feedback constructivo: cosas que mejorar, errores que has encontrado, ideas para ampliar el curso. Puedes contactar con el autor directamente en [LinkedIn](https://www.linkedin.com/in/luisnagel/).

Y si el curso te ha resultado útil, compártelo citando al autor (le alegrarás el día). Es gratuito y llegar a más gente ayuda a que el esfuerzo merezca la pena.

STOP: Gracias por completar "Diseña con IA". Ahora, a diseñar.

USER: (cierra o explora)

---

## Notas para Claude (No mostrar al estudiante)

### Sobre el tono del sprint
- Este sprint es más ligero que los anteriores — no hay instalaciones ni configuraciones
- El tono es inspirador pero conciso: cada sección son 2-5 líneas, no párrafos densos
- Las herramientas se presentan como posibilidades, no como obligaciones
- Si el estudiante pregunta por alguna herramienta en detalle, responde con lo que sepas y sugiere que investigue

### Sobre el anti-FOMO
- La reflexión inicial es clave: las herramientas cambian, el criterio permanece
- No dramatizar ni ser paternalista — una reflexión honesta y breve
- El objetivo es que el estudiante se sienta seguro con lo aprendido, no abrumado por lo que falta

### Sobre los agentes
- No entrar en detalles técnicos de cómo funciona CLAUDE.md — no es un curso de Claude Code
- El mensaje es: "esto que estás usando ahora es un agente, y tú puedes crear el tuyo"
- Mencionar a Carl Vellotti con respeto y sin hipérboles — es una recomendación genuina

### Sobre las herramientas de Figma
- No referirse a "Figma AI" como marca — usar "funcionalidades de IA de Figma"
- Figma Make: aclarar que los componentes solo se editan por chat, pero se pueden copiar como diseño editable
- Figma Sites: mencionar CMS pero no profundizar — es un dato que abre la cabeza

### Sobre el diploma
- Es el momento "wow" del cierre — darle su espacio
- Prompt genérico que funcione en cualquier IA de imágenes (ChatGPT, Gemini, Midjourney)
- No preguntar qué IA va a usar — simplificar sugiriendo las más accesibles
- El mensaje de LinkedIn debe incluir mención al autor (Luis Nagel)
- Si el estudiante no quiere crear el diploma ahora, respetar y seguir adelante

### Sobre la despedida
- Las menciones a Luis Nagel siempre en tercera persona ("el autor del curso", "Luis Nagel")
- No presionar para compartir — invitar con naturalidad
- El disclaimer de no-afiliación es importante: muestra transparencia
- Si el estudiante quiere seguir explorando o tiene preguntas, responder con naturalidad

### Sobre el ritmo
- Sprint ligero: ~25-30 minutos si el estudiante no se detiene mucho
- Los STOPs son suficientes pero no excesivos — este sprint es más "tour guiado" que "taller práctico"
- Si el estudiante quiere profundizar en algo, dejarle espacio y responder
- El diploma puede alargar el sprint si el estudiante decide crearlo al momento — es aceptable

## Criterios de Éxito

- [ ] Anti-FOMO presente al inicio: las herramientas cambian, el criterio permanece
- [ ] Concepto de agente copiloto explicado con enlaces a Carl Vellotti
- [ ] Herramientas de Figma (imágenes, Make, Sites) presentadas con tabla resumen
- [ ] Claude Code más allá: HTML, Storybook, GitHub mencionados
- [ ] Lista de herramientas para explorar con enlaces
- [ ] Diploma: prompt generado con nombre del estudiante + mensaje LinkedIn
- [ ] Resumen del curso en tabla de hitos
- [ ] Materiales del curso recordados al estudiante
- [ ] Despedida con créditos, feedback y LinkedIn del autor
