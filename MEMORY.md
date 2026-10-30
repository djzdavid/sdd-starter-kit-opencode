# Memoria del Proyecto (SDD)

## Estado Actual
- **Fase:** Inicialización del Proyecto.
- **Spec Activa:** Ninguna.

---

## Decisiones Globales de Arquitectura
- [Registrar aquí decisiones técnicas estructurales que apliquen a todo el repositorio a medida que avance el proyecto]

---

## Registro de Specs

| ID | Nombre de la Feature | Estado | Spec | Plan | Tareas |
| :--- | :--- | :--- | :---: | :---: | :---: |
| — | *Ninguna spec registrada aún* | — | — | — | — |

---

## Historial de Cambios Metodológicos y Gobernanza
- **[FECHA]:** Inicialización de la plantilla SDD. Constitución pendiente de configuración mediante `/sdd-constitution`.
- **2026-10-29:** Flujo ágil aprobado: paquete compacto, aprobación única, cuatro agentes, revisión final y evidencia reutilizable; comandos opcionales sin duplicación. Normalizado MEMORY.md. Sin cambios de modelos/MCP.
- **2026-10-29:** Corregido orden de permisos edit en coordinator/planner (deny general antes de excepciones); guardado de constitución directo por coordinator y comprobación posterior.
- **2026-10-29:** Documentado formato de patch y recuperación ante errores sintácticos sin nueva aprobación; verificar persistencia tras escritura.
- **2026-10-29:** Planner e implementer aplican frontend-design explícitamente para UI, con lectura directa alternativa y sin aprobaciones ni comprobaciones duplicadas.

- **2026-10-29:** Añadida plantilla docs/design-system.md; configuración junto a constitución, reutilización por agentes y cambios globales incluidos en aprobación del paquete. Coordinator con permiso documental específico.

- **2026-10-29:** Autorizada demo estática docs/design-system-demo.html previa a specs; implementer genera desde borrador, revisión y aprobación conjuntas con constitución, sin TDD ni código de aplicación.
