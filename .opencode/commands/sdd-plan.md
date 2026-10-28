---
description: SDD · Genera el plan técnico y el desglose de tareas consolidadas para una spec aprobada (Uso: /sdd-plan 001-nombre-feature)
agent: coordinator
---
Inicia la fase 3 (Plan técnico y Tareas) para la especificación ubicada en `specs/$1/`.

Instrucciones obligatorias para el flujo:
1. **Verificación Previa:** Confirma que `specs/$1/spec.md` esté en `Estado: aprobada` y sin dudas pendientes. Si está en borrador o inconclusa, **DETENTE** y notifica al usuario.
2. **Generación del Plan:** Pide a @planner crear `specs/$1/plan.md` (arquitectura, módulos, funciones puras, decisiones justificadas, estrategia de testing TDD y trazabilidad RF).
3. **Generación de Tareas Consolidadas:** Pide a @planner crear `specs/$1/tasks.md` desglosando la ejecución en un **MÁXIMO de 3 a 4 tareas principales consolidadas** para optimizar el consumo de tokens. Cada tarea debe tener su criterio `"Hecho cuando:"` medible mediante la suite de tests oficial de `docs/constitution.md`.
4. **Presentación y Aprobación:** Muestra el resumen del plan y las tareas en consola y **PARÁ a la espera de la aprobación explícita del usuario** antes de iniciar cualquier desarrollo.