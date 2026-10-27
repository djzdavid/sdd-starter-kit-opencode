---
description: SDD · Genera el plan técnico y el desglose de tareas para una spec aprobada (Uso: /sdd-plan 001-nombre-feature)
agent: planner
---
Lee `docs/constitution.md`, `AGENTS.md`, `MEMORY.md` y `specs/$1/spec.md` aplicando la skill sdd.

Regla previa obligatoria:
- Verifica que `specs/$1/spec.md` tenga la cabecera `Estado: aprobada` y no contenga marcadores `[NECESITA ACLARACIÓN]`. Si la spec está en borrador o con dudas pendientes, **DETENTE INMEDIATAMENTE** y notifica al usuario.

Instrucciones de generación:
1. **NO escribas código de producción.**
2. Genera `specs/$1/plan.md` cubriendo:
   - **Módulos y Archivos:** Archivos a crear o modificar con sus responsabilidades individuales.
   - **Lógica de Negocio:** Dominio, servicios, DTOs y funciones puras/deterministas.
   - **Algoritmos y Flujos:** Pseudocódigo de los flujos principales y transformaciones de datos.
   - **Capa de Interfaz / Presentación:** Componentes, vistas y contratos de datos (si aplica al alcance).
   - **Decisiones Justificadas:** Decisiones técnicas clave con sus alternativas descartadas y fundamentación.
   - **Estrategia de Testing:** Plan de pruebas unitarias y de integración acorde a la suite y ejecutor definidos en `docs/constitution.md`.
   - **Trazabilidad:** Mapeo explícito indicando qué Requisito Funcional (RF) de la spec cubre cada componente.
3. Genera `specs/$1/tasks.md`: Desglose en un máximo de 10 tareas atómicas (estimadas en 20-30 min cada una), ordenadas por dependencias lógicas, vinculadas a sus RF y con un criterio explícito de `"Hecho cuando:"` (medible mediante la suite de tests).