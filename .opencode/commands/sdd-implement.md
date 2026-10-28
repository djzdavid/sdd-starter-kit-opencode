---
description: SDD · Ejecuta la implementación TDD de la spec aprobada (Uso: /sdd-implement 001-nombre-feature)
agent: coordinator
---
Inicia la fase 4 (Implementación) para la especificación ubicada en `specs/$1/`.

Instrucciones obligatorias para el flujo:
1. **Delegación de Código:** Solicita a @implementer ejecutar las tareas pendientes de `specs/$1/tasks.md` siguiendo `specs/$1/plan.md` y `docs/constitution.md`.
2. **Flujo Continuo TDD:** Permite a @implementer avanzar en la ejecución continua de las tareas consolidadas sin frenos intermediarios innecesarios, respetando en cada paso el ciclo Red-Green-Refactor:
   - **Red:** Crear/actualizar tests y verificar que fallan.
   - **Green:** Escribir código de producción hasta hacerlos pasar.
   - **Verificación:** Ejecutar la suite de pruebas oficial y verificar componentes visuales con MCP si aplica.
3. **Control del Coordinador:** Tras la ejecución, confirma que toda la suite de pruebas pase en verde.
4. **Validación:** Si las tareas de la spec están completadas, pasa inmediatamente a la fase 5 llamando a @reviewer para validar el veredicto RF por RF.