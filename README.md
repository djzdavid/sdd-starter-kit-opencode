# Plantilla SDD para OpenCode

Desarrollo guiado por especificaciones y TDD, con cuatro agentes y una aprobación del paquete completo por feature.

## Inicio

1. Ejecuta `/sdd-constitution` para configurar stack, idioma y comandos reales del proyecto. Aprueba la propuesta completa; coordinator la guarda. Se hace al inicio, no por cada spec.
2. Ejecuta `/sdd-spec 001-mi-feature "Descripción"`. Planner prepara requisitos, enfoque técnico y tareas juntos. Las dudas bloqueantes se presentan agrupadas. La revisión previa independiente se reserva para riesgo elevado.
3. Revisa y aprueba el paquete guardado. Esa aprobación autoriza implementar, validar y cerrar de forma continua. Si quieres solo preparar, indícalo al pedir la spec.

Si dejaste un paquete aprobado pendiente, usa `/sdd-implement 001-mi-feature` para retomarlo. Este comando ya incluye validación y cierre: no hace falta ejecutar `/sdd-validate` después.

También puedes pedirlo en lenguaje natural al coordinator. No necesitas invocar cada agente ni cada fase manualmente.

## Agentes

- **Coordinator:** conduce el flujo, registra aprobación y estado, guarda constitución y actualiza memoria.
- **Planner:** prepara el paquete completo y revisa su coherencia en una ejecución.
- **Implementer:** ejecuta tareas con TDD continuo y entrega evidencia de pruebas y UI.
- **Reviewer:** revisa el resultado final RF por RF; revisa antes de implementar cuando el riesgo lo justifique.

Las asignaciones de modelos y el MCP permanecen en `opencode.json`. Los modelos/proveedores se configuran según el entorno de destino. La reducción de llamadas y contexto repetido busca disminuir tokens y latencia; el ahorro debe medirse en ejecuciones comparables.

## Documentos proporcionales

```text
.opencode/agents/             # Cuatro roles
.opencode/commands/           # Entradas al flujo
.opencode/skills/sdd/SKILL.md  # Formatos, estados y evidencia
.opencode/skills/frontend-design/
docs/constitution.md         # Stack y comandos del proyecto destino
specs/NNN-feature/spec.md     # Paquete compacto por defecto
specs/NNN-feature/plan.md     # Solo para formato extendido
specs/NNN-feature/tasks.md    # Solo para formato extendido
AGENTS.md                    # Reglas de colaboración y límites
MEMORY.md                    # Estado y decisiones ultracompactos
opencode.json                # Modelos y MCP
```

El paquete compacto contiene objetivo, RF verificables en EARS, límites, enfoque técnico, una a cuatro tareas y una tabla RF → prueba. Para varios módulos, integraciones, migraciones o arquitectura relevante, separar enfoque y tareas sin duplicar contenido. El detalle técnico va fuera de los RF.

## Aprobación y autonomía

La aprobación explícita del paquete guardado precede cualquier código de producción o pruebas. No se solicitan aprobaciones separadas de plan, tareas e implementación. Los cambios de alcance se preparan completos y se aprueban una vez. Migraciones, contratos y dependencias deben estar autorizados explícitamente o detallados en el enfoque técnico aprobado.

El agente resuelve detalles internos y fallos reparables dentro del alcance. Consulta si cambia el comportamiento, falta una decisión de negocio o aparece un bloqueo real. Tras dos rondas de correcciones sin resolver hallazgos finales, informa el bloqueo.

Estados en spec.md: `borrador` → `aprobada` → `en implementación` → `en validación` → `cerrada`. Registrar aprobación y alcance; tareas completas no equivalen a cierre.

## Verificación sin duplicaciones

Durante TDD se ejecutan pruebas afectadas; al finalizar, la suite completa oficial. Los agentes comparten evidencia comprobable del mismo estado del código. Se repite por cambios posteriores, evidencia insuficiente o riesgo concreto, con motivo explícito. La revisión final independiente se mantiene.

UI requiere comprobación del flujo, consola, red y vistas móvil/escritorio cuando aplique. Las herramientas ausentes y las comprobaciones pendientes se informan; impiden declarar validación completa. Esta plantilla no incluye una aplicación ni un ejecutor de tests: configura los comandos en la constitución del proyecto destino.

## Comandos

| Comando | Uso |
| --- | --- |
| `/sdd-constitution` | Configuración inicial de gobernanza |
| `/sdd-spec [nombre]` | Preparar paquete completo para aprobar |
| `/sdd-implement [nombre]` | Retomar implementación, validar y cerrar |
| `/sdd-change [nombre] "cambio"` | Preparar y aprobar un cambio de alcance |
| `/sdd-status [nombre]` | Consultar estado y siguiente acción |
| `/sdd-clarify [nombre]` | Auditoría puntual opcional de dudas/riesgos |
| `/sdd-plan [nombre]` | Ajustar enfoque y tareas, sin regeneración rutinaria |
| `/sdd-tasks [nombre]` | Ajustar solo tareas |
| `/sdd-validate [nombre]` | Reanudar o repetir validación con motivo |

No es necesario ejecutar los comandos opcionales en secuencia: el flujo principal ya realiza ese trabajo.

## Sistema de diseño compartido

Configura la identidad visual en `docs/design-system.md`: dirección visual, colores, tipografía, espaciado, componentes y estados, accesibilidad y adaptación. La plantilla deja valores pendientes para cada proyecto; no prescribe una marca ni una biblioteca.

`/sdd-constitution` propone esa base junto con las reglas técnicas cuando hay UI, con una sola aprobación. Si no hay UI se marca no aplica. Los detalles todavía innecesarios pueden quedar pendientes y resolverse en el paquete de la primera spec que los necesite.

Planner e implementer consultan el sistema y aplican `frontend-design` dentro de sus reglas; reviewer comprueba su cumplimiento. Los tokens y componentes reales viven en el código según el stack, implementados bajo una spec aprobada. Cualquier cambio global se presenta dentro del paquete de la spec, sin otra fase de aprobación.

## Vista previa antes de las specs

En proyectos con UI, `/sdd-constitution` prepara la base visual y genera `docs/design-system-demo.html` antes de pedir aprobación. Puedes aportar URLs o imágenes como referencia; el agente distingue lo observado de lo inferido y declara las limitaciones de acceso.

Revisa la demo de tipografía, colores, botones, campos, tarjetas y estados en escritorio/móvil, pide ajustes y aprueba la constitución y base visual juntas. Después empieza las features con `/sdd-spec`.

La demo es un prototipo HTML/CSS autónomo permitido explícitamente antes de cualquier spec, sin dependencias nuevas, servicios ni lógica de negocio. No exige TDD. Los tokens y componentes de aplicación siguen requiriendo una spec aprobada. El HTML concreto se genera en cada proyecto al definir su identidad; la plantilla no impone un diseño de ejemplo.
