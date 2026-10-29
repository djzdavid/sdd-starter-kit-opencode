# Guía de Trabajo del Asistente de IA

## Propósito y Contexto
Este archivo define la metodología de colaboración y los límites de actuación para el asistente de IA en este repositorio. Este proyecto utiliza estrictamente **Spec-Driven Development (SDD)**.

---

## Arquitectura y Gobernanza

La fuente de verdad técnica, el stack tecnológico (frameworks, base de datos, ejecutores de prueba), los convenios de código y las reglas específicas del proyecto están formalmente definidos en **`docs/constitution.md`**.

---

## Forma de Trabajar (Flujo SDD)

1. **Contexto:** Consultar `docs/constitution.md`, `MEMORY.md` y la spec activa una vez por ejecución; releer si cambian. La skill `.opencode/skills/sdd/SKILL.md` define formatos, estados y evidencia.
2. **Preparación conjunta:** Redactar requisitos, enfoque técnico y tareas en una ejecución. Formato compacto por defecto; documentos separados cuando la complejidad lo justifique.
3. **Aprobación única:** Presentar el paquete completo guardado y obtener aprobación explícita antes de escribir código de producción o pruebas. La aprobación autoriza implementación, validación y cierre continuos; respetar si el usuario solicita solo preparación.
4. **Clarificación:** Agrupar dudas de negocio bloqueantes durante la preparación. `/sdd-clarify` es opcional. Resolver detalles técnicos internos con las convenciones existentes.
5. **Cambios enfocados:** No anticipar funcionalidades. Cambios de comportamiento o alcance requieren actualizar el paquete y aprobar el cambio; no volver a aprobar decisiones vigentes.
6. **Cierre:** Revisión final independiente; revisión previa solo por riesgo justificado. Coordinator registra `cerrada` y actualiza memoria únicamente sin verificaciones obligatorias pendientes.

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
- **Rigor en la ejecución:** Ejecutar pruebas afectadas durante TDD y la suite completa al finalizar. Compartir evidencia válida del mismo estado del código entre agentes; repetir por cambios, evidencia insuficiente o riesgo concreto. Informar comando, resultado y estado verificado sin asumir comprobaciones no realizadas.

### 2. Verificación Visual e Interfaz de Usuario (si aplica)
- Para cambios en UI/frontend, utilizar las herramientas de inspección o emulación disponibles (navegador local / DevTools MCP).
- **Checklist de Inspección:**
  1. Navegar e interactuar con el flujo implementado en pantalla.
  2. Confirmar que no existan errores ni advertencias en la consola de JavaScript.
  3. Verificar en la pestaña de red (*Network*) las respuestas correctas de los endpoints.
  4. Comprobar la adaptabilidad en vistas móviles y de escritorio.

---

## Comandos SDD Disponibles

- `/sdd-constitution`: Configura la gobernanza inicial; coordinator guarda tras aprobación.
- `/sdd-spec [nombre]`: Prepara el paquete completo para una aprobación única.
- `/sdd-implement [nombre]`: Implementa, valida y cierra lo aprobado sin pausas rutinarias.
- `/sdd-change [nombre]`: Prepara un cambio completo y solicita aprobación del cambio.
- `/sdd-status [nombre]`: Consulta estado, evidencia pendiente y siguiente acción.
- Opcionales: `/sdd-clarify` audita dudas/riesgos, `/sdd-plan` ajusta enfoque y tareas, `/sdd-tasks` ajusta tareas, `/sdd-validate` reanuda o repite validación con motivo. No ejecutarlos después de pasos que ya realizaron ese trabajo.
