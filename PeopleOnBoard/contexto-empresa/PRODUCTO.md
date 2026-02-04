# Contexto del Producto PeopleOnBoard

## Descripción General
**PeopleOnBoard** es una plataforma "todo en uno" de gestión de RRHH diseñada específicamente para PYMES españolas. Combina la obligación legal del fichaje digital con herramientas para fomentar la cultura de empresa y la comunicación interna.

## Oportunidad de Mercado
La nueva legislación (Real Decreto 1155/2024) obliga a todas las empresas a tener un sistema de fichaje digital fiable y accesible.
*   **Problema:** Las soluciones actuales son demasiado complejas (suites enterprise caras) o demasiado simples (solo fichar, sin valor añadido).
*   **Solución:** PeopleOnBoard ofrece cumplimiento legal instantáneo + valor real para el empleado.
*   **Go-to-Market:** El foco en PYME se debe a la estrategia de distribución: **Partnership con Gestorías Laborales**. Ellas ya tienen la confianza de la PYME y gestionan sus nóminas, siendo el canal perfecto para prescribir la herramienta a cambio de comisión.

## Funcionalidades Clave (MVP)

### 1. Core: Fichaje Digital (Legal)
*   Registro de entrada/salida en 1 clic (< 5 segundos).
*   Geolocalización opcional (según política de empresa).
*   Registro y aprobación de horas extras.
*   Generación automática de informes para Inspección de Trabajo.

### 2. Portal del Empleado & Cultura
*   **Onboarding:** Acceso digital a documentación de bienvenida y manuales.
*   **Comunicación:** Tablón de anuncios (objetivos Q1/Q2, noticias).
*   **Documentación:** Repositorio de convenios, políticas y organigrama visual.
*   **Nóminas:** Visualización y descarga de nóminas (subidas por RRHH/Gestoría). No calcula nóminas, solo las distribuye.
*   **Formación:** Checklist de formaciones obligatorias (riesgos laborales, compliance) y recordatorios automáticos.

### 3. Gestión del Ciclo de Vida
*   **Vacaciones:** Solicitud y flujo de aprobación visual.
*   **Team Building:** Inscripción a actividades y eventos.
*   **Feedback:** Buzón de sugerencias y canal de denuncias (obligatorio por ley en ciertos casos).

### 4. Diferencial: AI Assistant
*   Agente conversacional inteligente que opera *dentro* de la intranet.
*   **Casos de uso:** Resolver dudas de gestión, encontrar información en documentos internos, guiar el onboarding de nuevos empleados y consultas de RRHH simples.

## Filosofía de Diseño

1.  **Simplicidad Radical:** Si una acción requiere manual de instrucciones, está mal diseñada. Fichar debe ser instantáneo.
2.  **Transparencia:** El estado de cualquier solicitud (vacaciones, horas extra) debe ser visible siempre para el empleado.
3.  **Human-Centric:** No es una herramienta de "vigilancia", es una herramienta de "gestión y pertenencia". El tono debe ser cercano.
4.  **Mobile-First (Mentalidad):** Aunque tenga versión web de escritorio, la mayoría de interacciones diarias ocurrirán en pantallas pequeñas o en momentos breves.

## Stack Tecnológico (Contexto para Diseño)
*   **Frontend:** React (componentes funcionales).
*   **Diseño:** Figma (Variables, Auto-layout).
*   **Documentación:** Storybook.
