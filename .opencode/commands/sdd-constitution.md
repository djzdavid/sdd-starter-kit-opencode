---
description: SDD · Configura la gobernanza una vez (Uso: /sdd-constitution "detalles")
agent: coordinator
---

Consulta AGENTS.md, MEMORY.md y docs/constitution.md. Información adicional: $ARGUMENTS.
Solicita al planner inspeccionar los archivos accesibles y proponer stack, arquitectura, política TDD y comandos, seguridad e idioma. No inventar tecnologías ni comandos no verificables; agrupa datos faltantes para el usuario.
Presenta la propuesta completa y espera aprobación explícita. Después coordinator guarda docs/constitution.md con sus permisos documentales y actualiza brevemente MEMORY.md. Planner no guarda fuera de specs/. No repetir esta configuración por cada feature ni pedir aprobación de nuevo si ya se autorizó la propuesta concreta.

El guardado es una acción directa del coordinator con la herramienta de escritura disponible siguiendo su esquema y las reglas de AGENTS.md, no una nueva tarea ni continuación del planner o reviewer. Tras escribir, lee ambos archivos para confirmar persistencia. Si la aprobación concreta ya consta en el chat, reutilízala sin solicitarla nuevamente.
