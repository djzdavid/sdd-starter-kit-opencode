---
description: SDD · Desglosa o regenera las tareas consolidadas a partir de un plan técnico (Uso: /sdd-tasks 001-nombre-feature)
agent: coordinator
---
Inicia la regeneración del desglose de tareas para la especificación ubicada en `specs/$1/`.

Instrucciones obligatorias para el flujo:
1. **Verificación Previa:** Confirma que `specs/$1/plan.md` exista y esté alineado con la spec aprobada. Si no existe, **DETENTE** y sugiere ejecutar primero `/sdd-plan $1`.
2. **Generación de Tareas Consolidadas:** Solicita a @planner crear o actualizar `specs/$1/tasks.md` bajo los siguientes criterios:
   - **NO escribir código de producción.**
   - Desglose consolidado en un **MÁXIMO de 3 a 4 tareas principales** por spec (evitar la hipergranularidad para optimizar tokens).
   - Secuenciadas en orden lógico de dependencias.
   - Cada tarea debe incluir:
     - Checkbox inicial desmarcado (`- [ ]`).
     - Identificador único (`T1`, `T2`, etc.).
     - Requisitos Funcionales (RF) que cubre.
     - Archivos afectados proyectados.
     - Criterio explícito e innegociable de `"Hecho cuando:"` (medible mediante la suite de tests oficial de `docs/constitution.md` o comprobación de interfaz).
3. **Presentación:** Muestra el desglose de tareas al usuario y solicita su confirmación explícita antes de iniciar la implementación.