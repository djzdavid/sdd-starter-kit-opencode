# Plantilla SDD (Spec-Driven Development) para OpenCode

Esta plantilla proporciona un flujo de desarrollo riguroso, portable y 100% agnóstico del stack tecnológico, guiado por especificaciones (Spec-Driven Development) y desarrollo guiado por pruebas (TDD).

---

## Estructura del Repositorio

.
├── .opencode/
│   ├── agents/          # Subagentes (coordinator, planner, implementer, reviewer)
│   ├── commands/        # Comandos del ciclo de vida SDD (/sdd-*)
│   └── skills/          # Skills portátiles (sdd)
├── docs/
│   └── constitution.md  # Reglas innegociables con marcadores [PENDIENTE] (se configura al inicio)
├── specs/               # Especificaciones funcionales por característica
├── AGENTS.md            # Guía de colaboración para el asistente de IA
├── MEMORY.md            # Registro ultracompacto de estado y decisiones globales
└── opencode.json        # Configuración del entorno OpenCode (model routing & token limits)

---

## Dos Formas de Trabajar

Puedes interactuar con la plantilla de dos maneras según tu preferencia:

1. Conversacional (Hablando con el coordinator):
   Puedes pedirle tareas directamente en lenguaje natural al subagente orquestador y él se encargará de delegar internamente al agente especializado (planner, implementer o reviewer):
   - "Hola coordinador, vamos a configurar la constitución del proyecto."
   - "Coordinador, quiero redactar una spec para el módulo de autenticación."
   - "Coordinador, empieza a implementar las tareas pendientes usando TDD."

2. Mediante Comandos Atajo (/sdd-*):
   Si prefieres ir al grano sin redactar mensajes, usa las órdenes directas en el chat (por ejemplo, /sdd-constitution, /sdd-spec, /sdd-implement).

---

## Paso a Paso: Cómo Iniciar un Proyecto Nuevo

Una vez que hayas clonado este repositorio plantilla para tu nuevo proyecto, abre el chat de OpenCode y sigue esta secuencia:

### Paso 1: Configurar la Constitución Técnica
Escribe en el chat:
/sdd-constitution

Qué sucederá: El agente analizará tu repositorio e inspeccionará los archivos del proyecto para reemplazar los marcadores [PENDIENTE] en docs/constitution.md con el stack tecnológico, framework de tests, convenios de idioma y comandos oficiales. Te pedirá confirmación antes de guardar.

---

### Paso 2: Crear la Primera Especificación (Spec)
Escribe en el chat detallando la característica que deseas construir:
/sdd-spec NNN-mi-nueva-feature "Descripción inicial de la idea"

Qué sucederá: El agente planner creará el borrador en specs/NNN-mi-nueva-feature/spec.md utilizando la plantilla oficial de la skill SDD en formato EARS (Requisitos Funcionales, Casos Límite y Criterios de Aceptación).

---

### Paso 3: Aclarar Dudas y Auditar QA
Audita la especificación para resolver ambigüedades antes de planificar:
/sdd-clarify NNN-mi-nueva-feature

Qué sucederá: El agente reviewer revisará la spec como QA. Si detecta puntos ambiguos de negocio, te presentará preguntas breves para definir el comportamiento exacto antes de dar la spec por aprobada.

---

### Paso 4: Generar el Plan Técnico y Tareas Consolidadas
Una vez aprobada la spec, genera la arquitectura y el desglose de tareas:
/sdd-plan NNN-mi-nueva-feature

y posteriormente:
/sdd-tasks NNN-mi-nueva-feature

Qué sucederá: Se crearán los archivos plan.md y tasks.md dentro de la carpeta de la spec, desglosando la implementación en un máximo de 3 a 4 tareas principales consolidadas por spec para optimizar tokens y asegurar ejecuciones TDD fluidas.

---

### Paso 5: Implementar guiado por TDD
Para comenzar a escribir código:
/sdd-implement NNN-mi-nueva-feature

Qué sucederá: El agente implementer tomará las tareas de tasks.md, creará primero las pruebas unitarias/integración en rojo, escribirá el código mínimo para pasarlas a verde y completará el ciclo Red-Green-Refactor.

---

### Paso 6: Validar y Auditar el Cumplimiento
Al finalizar la implementación, audita el resultado final:
/sdd-validate NNN-mi-nueva-feature

Qué sucederá: El agente reviewer ejecutará la suite completa de pruebas, verificará el cumplimiento Requisito Funcional por Requisito Funcional (RF) y entregará el veredicto (APROBADO o CAMBIOS NECESARIOS). Si es aprobado, el coordinator cerrará la spec y actualizará MEMORY.md.

---

## Resumen de Comandos Rápidos

- /sdd-constitution: Configura el stack, reglas y comandos en docs/constitution.md.
- /sdd-spec [nombre]: Crea o edita la especificación en borrador (EARS).
- /sdd-clarify [nombre]: Audita la spec como QA y resuelve ambigüedades.
- /sdd-plan [nombre]: Diseña la arquitectura y plan técnico (plan.md).
- /sdd-tasks [nombre]: Genera el desglose de tareas consolidadas (máx 3-4).
- /sdd-implement [nombre]: Ejecuta la implementación guiada estrictamente por TDD.
- /sdd-validate [nombre]: Audita RF por RF con tests/MCP visual y cierra la spec.
- /sdd-change [nombre]: Gestiona cambios de alcance o requerimientos.
- /sdd-status [nombre]: Muestra la fase actual y el porcentaje de progreso.