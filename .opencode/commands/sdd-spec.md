---
description: SDD · Entrevista al usuario y redacta la spec inicial en borrador (Uso: /sdd-spec 001-nombre-feature "Descripción inicial de la idea")
agent: planner
---
NO escribas ni modifiques código de la aplicación. Lee `docs/constitution.md`, `MEMORY.md` y aplica las reglas de la skill sdd.

Carpeta objetivo: `specs/$1/`
Idea o contexto inicial: $ARGUMENTS

Flujo de trabajo:
1. **Entrevista de Clarificación:** Si la idea o el alcance presentan ambigüedades de negocio, haz una lista numerada con un **máximo de 5 preguntas clave** para resolver casos límite, escenarios de error o elementos fuera de alcance. NO generes la spec hasta recibir las respuestas.
2. **Generación de Spec:** Una vez resueltas las dudas (o si la idea inicial es totalmente clara y autosuficiente), crea o actualiza el archivo `specs/$1/spec.md` siguiendo estrictamente la plantilla de la skill sdd.
3. **Estructura y Reglas:**
   - Marca el archivo con `Estado: borrador`.
   - Redacta todos los Requisitos Funcionales (RF) utilizando la sintaxis EARS (`CUANDO...`, `SI... ENTONCES...`, `MIENTRAS...`, `EL SISTEMA DEBERÁ...`).
   - Enfócate **única y exclusivamente en el QUÉ y el POR QUÉ**: queda estrictamente prohibido incluir stack tecnológico, arquitectura, base de datos o nombres de archivos de código fuente.