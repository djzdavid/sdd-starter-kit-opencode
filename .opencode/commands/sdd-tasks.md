---
description: SDD · Desglosa o regenera las tareas atómicas a partir de un plan técnico (Uso: /sdd-tasks 001-nombre-feature)
agent: planner
---
Lee `docs/constitution.md`, `specs/$1/spec.md` y `specs/$1/plan.md` aplicando la skill sdd.

Regla previa obligatoria:
- Verifica que `specs/$1/plan.md` exista y esté alineado con la spec aprobada. Si no existe `plan.md`, **DETENTE INMEDIATAMENTE** y sugiere ejecutar primero `/sdd-plan $1`.

Instrucciones de generación:
1. **NO escribas código de producción.**
2. Genera o actualiza `specs/$1/tasks.md` siguiendo estas reglas:
   - Tareas pequeñas, atómicas e independientes (estimadas en 20-30 minutos de trabajo cada una).
   - Secuenciadas estrictamente en orden lógico de dependencias de implementación.
   - Cada tarea debe incluir:
     - Checkbox inicial desmarcado (`- [ ]`).
     - Identificador único (`T1`, `T2`, etc.).
     - Requisitos Funcionales (RF) de la spec que cubre.
     - Archivos afectados proyectados.
     - Criterio explícito e innegociable de `"Hecho cuando:"` (medible objetivamente mediante la suite de tests definida en `docs/constitution.md` o verificación visual de interfaz).
3. **Límite de alcance:** El total no debe superar las 10 tareas. Si el desglose requiere más de 10 tareas, **NO escribas `tasks.md`**, detente y propone al usuario dividir la spec en dos o más iteraciones o sub-features más pequeñas.