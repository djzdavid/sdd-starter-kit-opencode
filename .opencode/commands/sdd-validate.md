---
description: SDD · Audita y valida la implementación de la spec RF por RF mediante la suite de tests y el MCP visual (Uso: /sdd-validate 001-nombre-feature)
agent: coordinator
---
Inicia la fase 5 y 7 (Validación de QA y Cierre) para la especificación ubicada en `specs/$1/`.

Instrucciones obligatorias para el flujo:
1. **Delegación de Auditoría:** Solicita a @reviewer auditar `specs/$1/` con las siguientes directrices:
   - **NO modificar ningún archivo.**
   - Consultar `docs/constitution.md` para ejecutar la suite de pruebas oficial.
   - Analizar cambios de código (`git status`, `git diff`).
   - Auditar **Requisito Funcional por Requisito Funcional (RF)** indicando el test que lo cubre o usando el MCP de inspección visual si aplica.
   - Entregar OBLIGATORIAMENTE el veredicto: `VEREDICTO: APROBADO` o `VEREDICTO: CAMBIOS NECESARIOS`.
2. **Procesamiento del Veredicto:**
   - Si es **CAMBIOS NECESARIOS**: Presenta la lista de hallazgos al usuario y reasigna automáticamente las correcciones a @implementer.
   - Si es **APROBADO**: Resume el veredicto, notifica al usuario y **actualiza `MEMORY.md`** con el registro del cierre en formato ultracompacto.