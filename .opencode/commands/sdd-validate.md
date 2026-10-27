---
description: SDD · Audita y valida la implementación de la spec RF por RF mediante la suite de tests y el MCP visual (Uso: /sdd-validate 001-nombre-feature)
agent: reviewer
---
Realiza una auditoría completa de la implementación de la spec ubicada en `specs/$1/`.

Instrucciones de revisión:
1. **NO modifiques ningún archivo de código ni de documentación (`edit: deny`).**
2. **Consulta de Reglas e Infraestructura:** Lee `docs/constitution.md` para obtener el comando oficial de ejecución de pruebas y los principios innegociables del proyecto.
3. **Lectura de Especificación:** Lee `specs/$1/spec.md`, `specs/$1/plan.md` y `specs/$1/tasks.md`.
4. **Ejecución de Pruebas:** Ejecuta la suite de pruebas automatizadas en la consola utilizando el comando oficial definido en la Constitución.
5. **Auditoría Requisito por Requisito:** Recorre `spec.md` **Requisito Funcional por Requisito Funcional (RF)**:
   - Para cada RF de lógica de negocio o backend, indica qué prueba específica lo cubre y confirma su paso en verde.
   - Para cada RF de interfaz de usuario o componentes visuales, verifícalo mediante el MCP de inspección de navegador disponible (incluida la comprobación en vista móvil a 375px si aplica).
6. **Cumplimiento Global:** Comprueba la adhesión a los **Criterios de Finalización** definidos en la spec y el cumplimiento de los principios innegociables de `docs/constitution.md`.

Estructura obligatoria de la respuesta:
Empieza tu mensaje OBLIGATORIAMENTE con una de estas dos líneas:
- **VEREDICTO: APROBADO**
- **VEREDICTO: CAMBIOS NECESARIOS**

Si el veredicto es **CAMBIOS NECESARIOS**, entrega una lista numerada detallando: `archivo:línea`, el RF o principio incumplido y el comportamiento esperado. *(Si hay sugerencias opcionales de refactorización que no violen la spec, inclúyelas al final en una sección llamada "Opcional")*.