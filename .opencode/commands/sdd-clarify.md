---
description: SDD · Audita la spec como QA detectando ambigüedades sin editar archivos (Uso: /sdd-clarify 001-nombre-feature)
agent: coordinator
---
Inicia la fase 2 (Clarificación / QA Audit) para la especificación ubicada en `specs/$1/spec.md`.

Instrucciones obligatorias para el flujo:
1. **Auditoría de QA:** Pide a @reviewer que lea `specs/$1/spec.md` y `docs/constitution.md` y reporte de forma sintética:
   - **Ambigüedades restantes:** Requisitos no medibles u objetivamente verificables.
   - **Contradicciones:** Inconsistencias entre RFs o con el alcance.
   - **Casos límite no cubiertos:** Escenarios de error, límites de datos o fallos omitidos.
   - **Conflictos con la Constitución:** Violaciones a `docs/constitution.md`.
2. **Restricción de Edición:** Asegúrate de que @reviewer NO modifique ningún archivo ni proponga código/soluciones.
3. **Manejo de Resultados:**
   - Si @reviewer indica `"Sin observaciones. La spec está lista para aprobación."`, presenta el resultado y solicita la aprobación explícita del usuario.
   - Si existen observaciones, presenta la lista al usuario y solicita a @planner corregir `spec.md` antes de pedir la aprobación final.