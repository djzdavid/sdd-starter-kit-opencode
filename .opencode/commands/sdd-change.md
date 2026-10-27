---
description: SDD · Aplica un cambio o nuevo requisito actualizando spec.md primero (Uso: /sdd-change 001-nombre "Descripción del cambio")
agent: planner
---
Gestión de cambio de requisitos para la especificación ubicada en `specs/$1/`.

Contexto y descripción del cambio: $ARGUMENTS

Instrucciones obligatorias:
1. **Verificación de Reglas:** Consulta `docs/constitution.md` para asegurar que la solicitud de cambio no contravenga ningún principio innegociable.
2. **NO toques código de producción.**
3. **Actualización de Spec (`spec.md`):**
   - Redacta o modifica los Requisitos Funcionales (RF) afectados utilizando la sintaxis EARS.
   - Define los casos límite, escenarios de error y elementos fuera de alcance asociados al cambio.
4. **Impacto Estimado:** Identifica y reporta qué secciones de `plan.md` y `tasks.md` requerirán actualización posterior.
5. **Aprobación Obligatoria:** Muestra un resumen claro con las modificaciones aplicadas a `spec.md` y **DETENTE** a la espera de la aprobación explícita del usuario.