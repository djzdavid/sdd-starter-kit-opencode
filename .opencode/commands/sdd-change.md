---
description: SDD · Aplica un cambio o nuevo requisito actualizando spec.md primero (Uso: /sdd-change 001-nombre "Descripción del cambio")
agent: coordinator
---
Gestión de cambio de requisitos para la especificación ubicada en `specs/$1/`.

Contexto y descripción del cambio: $ARGUMENTS

Instrucciones obligatorias para el flujo:
1. **Verificación de Reglas:** Consulta `docs/constitution.md` para asegurar que el cambio no contravenga ningún principio innegociable.
2. **Delegación a Spec:** Solicita a @planner actualizar `specs/$1/spec.md`:
   - Redactar o modificar los Requisitos Funcionales (RF) afectados utilizando sintaxis EARS.
   - Definir casos límite, escenarios de error y elementos fuera de alcance.
   - **Garantizar que NO se toque código de producción.**
3. **Impacto Estimado:** Muestra al usuario el resumen del diff en `spec.md` e indica qué partes de `plan.md` y `tasks.md` requerirán actualización.
4. **Aprobación del Usuario:** **PARÁ y espera** la aprobación explícita del usuario.
5. **Actualización de Plan y Tareas:** Tras la aprobación, solicita a @planner actualizar `plan.md` y `tasks.md`, manteniendo el desglose consolidado en **máximo 3 a 4 tareas principales** para proteger el consumo de tokens.