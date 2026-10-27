---
name: sdd
description: "Úsala siempre que trabajes con Spec-Driven Development en este proyecto (docs/constitution.md o cualquier archivo dentro de specs/) - redactar, revisar o cambiar specs, planes y tareas, o implementar y validar tareas de una spec."
---

# Spec-Driven Development (SDD)

## Flujo
Constitución → Spec → Clarificación → Plan → Tareas → Implementación → Validación → Cambio.
- Nunca pases a la siguiente fase sin la aprobación explícita del usuario.
- La spec manda: si algo no está en la spec, no se implementa. Si falta una decisión de negocio, detente y consulta al usuario.
- Un cambio de requisitos se actualiza primero en la spec (`spec.md`), posteriormente en el plan (`plan.md`) y las tareas (`tasks.md`), y finalmente en el código fuente.
- Cada especificación vive en su propia carpeta: `specs/NNN-nombre/` conteniendo `spec.md`, `plan.md` y `tasks.md`.
- Al finalizar cada fase, actualiza el estado en `MEMORY.md`.

---

## Plantilla de Especificación (`specs/NNN-nombre/spec.md`)

```markdown
# Spec NNN — <Nombre de la Feature>
Estado: borrador | aprobada | implementada

## Contexto y objetivo
## Usuarios / Roles
## Historias de usuario
- HU-1: Como <rol>, quiero <acción> para <beneficio>.

## Definiciones
- Términos de dominio o negocio propensos a ambigüedad.

## Requisitos Funcionales (Sintaxis EARS)
- RF-1: CUANDO <disparador/evento>, EL SISTEMA DEBERÁ <acción>.
- RF-2: SI <condición no deseada/error>, ENTONCES EL SISTEMA DEBERÁ <respuesta de mitigación>.
- RF-3: MIENTRAS <estado activo>, EL SISTEMA DEBERÁ <comportamiento continuo>.
- RF-4: EL SISTEMA DEBERÁ <requisito permanente/ubicuo>.

*Nota: Cada Requisito Funcional (RF) debe ser 100% verificable mediante pruebas automatizadas o comprobación visual. Evita adjetivos ambiguos como "rápido", "robusto" o "fácil" sin métricas concretas.*

## Requisitos No Funcionales
## Casos Límite y Escenarios de Error
## Fuera de Alcance
## Criterios de Finalización
## Dudas Abiertas
- [NECESITA ACLARACIÓN] <Pregunta o ambigüedad de negocio pendiente>
```

---

## Estructura del Plan Técnico (`specs/NNN-nombre/plan.md`)

- **Estrategia de Testing:** Plan de pruebas unitarias y de integración según la suite y el ejecutor configurados en `docs/constitution.md`.
- **Módulos y Archivos:** Estructura de archivos a crear/modificar con sus responsabilidades individuales.
- **Lógica de Negocio:** Dominio, DTOs y funciones puras/deterministas.
- **Algoritmos y Flujos:** Pseudocódigo de las transformaciones y flujos de datos principales.
- **Capa de Interfaz / Presentación:** Componentes visuales y contratos de datos envolvientes (si aplica).
- **Decisiones Justificadas:** Decisiones técnicas clave con sus alternativas descartadas.
- **Trazabilidad:** Mapeo explícito indicando qué Requisito Funcional (RF) cubre cada componente.

---

## Estructura de Tareas (`specs/NNN-nombre/tasks.md`)

- [ ] **T1. <Descripción corta de la acción>.** RF-1, RF-2
  - **Archivos proyectados:** `src/Domain/...`, `tests/...`
  - **Hecho cuando:** <Criterio de aceptación verificable con test en verde o inspección en UI>.
- [ ] **T2. <Descripción atómica de la siguiente tarea>.** RF-3
  - **Archivos proyectados:** `src/UI/...`
  - **Hecho cuando:** <Criterio de aceptación verificable>.
```