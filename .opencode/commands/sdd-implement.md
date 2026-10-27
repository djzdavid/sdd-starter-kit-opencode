---
description: SDD · Implementa UNA sola tarea aplicando TDD (Uso: /sdd-implement 001-nombre-feature T1)
agent: implementer
---
Implementa únicamente la tarea $2 definida en `specs/$1/tasks.md`, siguiendo las directrices de `specs/$1/plan.md`, `docs/constitution.md` y la skill sdd.

Pasos obligatorios:
1. **Consulta de Infraestructura:** Lee `docs/constitution.md` para identificar el marco de pruebas y el comando ejecutor de tests oficial del proyecto.
2. **Tests primero (Red):** Escribe o actualiza los tests correspondientes para la tarea $2 y ejecuta el comando de pruebas del proyecto para confirmar que fallan.
3. **Código de producción (Green):** Escribe el código estrictamente necesario para hacer pasar los tests.
4. **Verificación:** Ejecuta el comando de pruebas del proyecto y confirma que la suite pasa en verde. Si la tarea involucra componentes visuales o de interfaz de usuario, verifícalos mediante el MCP de inspección de navegador disponible.
5. **Cierre de Tarea:** Marca únicamente la tarea $2 como completada en `specs/$1/tasks.md` (`- [x]`), reporta los Requisitos Funcionales (RF) que cubre y los archivos modificados.

Regla de parada estricta:
- **DETENTE INMEDIATAMENTE** tras completar la tarea $2. No inicies la siguiente tarea bajo ninguna circunstancia.
- Si $2 es la última tarea de `tasks.md`, actualiza `MEMORY.md` notificando la finalización de la fase de implementación.