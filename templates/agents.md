# Guía de Trabajo del Asistente de IA

## Propósito y Contexto
Este archivo define la metodología de colaboración y los límites de actuación para el asistente de IA en este repositorio. Este proyecto utiliza estrictamente **Spec-Driven Development (SDD)**.

---

## Arquitectura y Gobernanza

La fuente de verdad técnica, el stack tecnológico (frameworks, base de datos, ejecutores de prueba), los convenios de código y las reglas específicas del proyecto están formalmente definidos en **`docs/constitution.md`**.

---

## Forma de Trabajar (Flujo SDD)

1. **Lectura Obligatoria Previa:** Consultar siempre `docs/constitution.md`, `MEMORY.md` y la especificación activa dentro de `specs/` antes de responder, planificar o modificar código.
2. **Gobernanza de Especificación:** Ninguna línea de código de producción o de prueba existe sin una especificación previamente aprobada en la carpeta `specs/`. Un borrador o propuesta en chat no autoriza implementar.
3. **Cambios Enfocados:** Realizar cambios pequeños, atómicos y estrictamente vinculados al alcance de la tarea actual. No generar estructuras abstractas ni funcionalidades futuras por anticipado.
4. **Claridad y Confirmación:** Explicar las decisiones con claridad y solicitar aclaraciones mediante `/sdd-clarify` ante cualquier ambigüedad de negocio.
5. **Cierre de Tareas:** Al finalizar cada tarea, resumir los cambios realizados, reportar los resultados de los tests ejecutados y actualizar `MEMORY.md`.

---

## Límites de Actuación

### ✅ Siempre
- Responder y redactar la documentación en el idioma establecido en `docs/constitution.md`.
- Respetar la arquitectura, convenciones de tipado estricto y estándares definidos en la constitución.
- Validar, sanitizar y convertir tipos de las entradas externas antes de persistirlas o procesarlas.
- Preservar la trazabilidad y la inmutabilidad de los registros históricos de datos.

### ⚠ Pregunta Antes
- Crear o modificar migraciones y esquemas de base de datos.
- Alterar contratos de API, endpoints o DTOs existentes.
- Agregar o eliminar dependencias/paquetes del proyecto.

*Estas acciones requieren autorización explícita o estar expresamente detalladas en el plan técnico de la spec aprobada.*

### 🚫 Nunca
- Agregar, refactorizar o modificar código de producción sin una spec aprobada que lo cubra.
- Escribir en duro (*hardcode*) valores normativos, variables de entorno, credenciales o datos de configuración en el código base.
- Persistir datos inválidos o silenciar errores críticos con valores de reemplazo por defecto.
- Guardar credenciales, tokens o datos sensibles en repositorios, documentación o archivos de memoria.

---

## Verificación y Calidad de Funcionalidades

### 1. Pruebas Automatizadas (TDD)
- **Estrategia:** Consultar en `docs/constitution.md` el ejecutor y comando oficial de pruebas del proyecto.
- **Enfoque TDD:** Toda tarea debe implementar sus pruebas correspondientes (unitarias/integración) antes o en paralelo al código de producción.
- **Aislamiento:** Aislar dependencias externas e integraciones mediante respuestas simuladas (*mocks* / *fixtures* controlados).
- **Rigor en la ejecución:** Ejecutar la suite de pruebas pertinente antes de dar por completada una tarea. Informar los resultados con transparencia sin asumir verificaciones no realizadas.

### 2. Verificación Visual e Interfaz de Usuario (si aplica)
- Para cambios en UI/frontend, utilizar las herramientas de inspección o emulación disponibles (navegador local / DevTools MCP).
- **Checklist de Inspección:**
  1. Navegar e interactuar con el flujo implementado en pantalla.
  2. Confirmar que no existan errores ni advertencias en la consola de JavaScript.
  3. Verificar en la pestaña de red (*Network*) las respuestas correctas de los endpoints.
  4. Comprobar la adaptabilidad en vistas móviles y de escritorio.

---

## Comandos SDD Disponibles

- `/sdd-constitution`: Define o actualiza las reglas técnicas innegociables.
- `/sdd-spec [nombre-feature]`: Crea o actualiza una especificación (EARS).
- `/sdd-clarify [nombre-feature]`: Despeja ambigüedades de negocio.
- `/sdd-plan [nombre-feature]`: Diseña la arquitectura y plan técnico.
- `/sdd-tasks [nombre-feature]`: Desglosa las tareas atómicas.
- `/sdd-implement [nombre-feature]`: Implementa el código guiado por TDD.
- `/sdd-validate [nombre-feature]`: Audita el cumplimiento de la spec.
- `/sdd-change [nombre-feature]`: Gestiona cambios de alcance o requerimientos.
- `/sdd-status`: Muestra el estado actual del proyecto.