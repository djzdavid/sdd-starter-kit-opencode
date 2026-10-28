---
description: SDD · Informa la fase actual, el progreso de tareas y sugiere el siguiente comando (Uso: /sdd-status 001-nombre-feature)
agent: coordinator
---
Lee minuciosamente los archivos de `specs/$1/` (`spec.md`, `plan.md` y `tasks.md`, según existan) y el estado global registrado en `MEMORY.md`.

Instrucciones:
1. **Identifica la Fase Actual:**
   - **Fase 1 (Spec):** Si `spec.md` está en `Estado: borrador`.
   - **Fase 2 (Clarificación):** Si `spec.md` está redactada y pendiente de auditoría de QA.
   - **Fase 3 (Planificación):** Si `spec.md` está en `Estado: aprobada` pero no existen `plan.md` o `tasks.md` (o están pendientes de aprobación).
   - **Fase 4 (Implementación):** Si existe `tasks.md` con tareas pendientes (`- [ ]`).
   - **Fase 5/6 (Validación/Cierre):** Si el 100% de las tareas en `tasks.md` están marcadas como completadas (`- [x]`).
2. **Reporta el Progreso:** Informa el conteo exacto de tareas completadas respecto al total (ej. `3/4 tareas completadas (75%)`).
3. **Determina el Siguiente Paso:** Indica la acción inmediata requerida y sugiere el comando exacto a ejecutar (`/sdd-clarify`, `/sdd-plan`, `/sdd-implement`, `/sdd-verify`, etc.).

Regla estricta:
- **NO modifiques ningún archivo.** Entrega la respuesta de forma clara y estructurada en un máximo de 8 líneas.