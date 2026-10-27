---
description: SDD · Audita la spec como QA detectando ambigüedades sin editar archivos (Uso: /sdd-clarify 001-nombre-feature)
agent: reviewer
---
Actúa como QA Senior y audita `specs/$1/spec.md` aplicando la skill sdd.

Instrucciones:
1. Lee minuciosamente `specs/$1/spec.md` y `docs/constitution.md`.
2. Identifica y reporta problemas organizados en una lista numerada bajo estas 4 categorías:
   1. **Ambigüedades restantes:** Requisitos que no son medibles ni verificables objetivamente mediante tests o inspección visual.
   2. **Contradicciones:** Inconsistencias entre los Requisitos Funcionales (RF) o con el alcance definido.
   3. **Casos límite no cubiertos:** Escenarios de error, límites de datos o fallos de red/fuentes externas omitidos.
   4. **Conflictos con la Constitución:** Violaciones a los principios innegociables declarados en `docs/constitution.md`.

Reglas estrictas:
- **NO modifiques ningún archivo (`edit: deny`).**
- **NO propongas soluciones, código ni arquitectura:** concéntrate únicamente en señalar las fallas o vacíos detectados.
- Si no encuentras ningún problema, responde explícitamente: `"Sin observaciones. La spec está lista para aprobación."`