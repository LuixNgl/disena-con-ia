# Actualizar el curso

Descarga las últimas actualizaciones del curso desde GitHub sin modificar el trabajo del estudiante.

## Qué actualizar y qué proteger

**Actualizar (archivos del curso):**
- `.claude/` — scripts de sprints y agente instructor
- `materiales/` — templates y recursos
- `PeopleOnBoard/contexto-empresa/` — contexto del caso
- `PeopleOnBoard/entrevistas-usuario/` — entrevistas
- `README.md` — presentación del curso

**Nunca tocar:**
- `PeopleOnBoard/outputs/` — todo el trabajo del estudiante

## Proceso

ACTION: Antes de ejecutar nada, explica al estudiante:

> Voy a descargar las últimas actualizaciones del curso. Tu trabajo en `PeopleOnBoard/outputs/` no se tocará. Cursor me pedirá permiso para ejecutar un comando — selecciona "Allow".

ACTION: Ejecuta en Bash (como un solo bloque):

    # Inicializar git si no existe
    git rev-parse --git-dir 2>/dev/null || git init

    # Configurar el remoto si no existe
    git remote get-url origin 2>/dev/null || git remote add origin https://github.com/LuixNgl/disena-con-ia.git

    # Descargar los últimos cambios
    git fetch origin

    # Aplicar actualizaciones — nunca toca outputs/
    git checkout FETCH_HEAD -- .claude/ materiales/ PeopleOnBoard/contexto-empresa/ PeopleOnBoard/entrevistas-usuario/ README.md 2>/dev/null; echo "COMPLETADO"

ACTION: Confirma el resultado:

> Listo. Los scripts y materiales del curso están al día. Tu trabajo en `PeopleOnBoard/outputs/` sigue intacto.
>
> Si estabas en mitad de un sprint, puedes retomarlo exactamente donde lo dejaste.

[Si hay errores, ayuda a resolverlos antes de continuar:]
- **Sin conexión:** Pide al estudiante verificar la red e intentarlo de nuevo
- **git no instalado:** Indicar que lo descargue desde git-scm.com (o Xcode Command Line Tools en Mac: `xcode-select --install`)
- **Permisos denegados:** Verificar que la carpeta del curso no está en modo solo lectura
