# Plantilla SDD (Spec-Driven Development) para OpenCode

Esta plantilla proporciona un flujo de desarrollo riguroso, portable y 100% agnóstico del stack tecnológico, guiado por especificaciones (**Spec-Driven Development**) y desarrollo guiado por pruebas (**TDD**).

---

## 📁 Estructura del Repositorio

```text
.
├── .opencode/
│   ├── agents/          # Subagentes (coordinator, planner, implementer, reviewer)
│   ├── commands/        # Comandos del ciclo de vida SDD (/sdd-*)
│   ├── skills/          # Skills portátiles (sdd, frontend-design)
│   └── templates/       # Plantillas base (constitution, MEMORY, spec)
├── docs/
│   └── constitution.md  # Reglas innegociables y comandos del proyecto (se genera al inicio)
├── specs/               # Especificaciones funcionales por característica
├── AGENTS.md            # Guía de colaboración para el asistente de IA
├── MEMORY.md            # Registro de estado y decisiones de arquitectura
└── opencode.json        # Configuración del entorno OpenCode
```

---

## 🚀 Paso a Paso: Cómo Iniciar un Proyecto Nuevo

Una vez que hayas clonado este repositorio plantilla para tu nuevo proyecto, abre el chat de OpenCode y sigue esta secuencia:

### Paso 1: Configurar la Constitución Técnica
Escribe en el chat:
```text
/sdd-constitution
```
> **Qué sucederá:** El agente analizará tu repositorio y te hará una breve entrevista en el chat para definir el stack tecnológico, la base de datos, el framework de tests, los convenios de idioma y los comandos oficiales de ejecución. Al finalizar, creará automáticamente el archivo `docs/constitution.md` y actualizará `MEMORY.md`.

---

### Paso 2: Crear la Primera Especificación (Spec)
Escribe en el chat detallando la característica que deseas construir:
```text
/sdd-spec mi-nueva-feature
```
> **Qué sucederá:** El agente `planner` creará el borrador en `specs/NNN-mi-nueva-feature/spec.md` utilizando sintaxis EARS (Requisitos Funcionales, Casos Límite y Criterios de Aceptación). Te pedirá confirmación antes de darla por aprobada.

---

### Paso 3: Aclarar Dudas y Ambigüedades (Opcional)
Si la especificación requiere ajustar detalles de negocio o casos borde:
```text
/sdd-clarify mi-nueva-feature
```
> **Qué sucederá:** El agente detectará los puntos ambiguos y te presentará preguntas estructuradas con opciones para que elijas el comportamiento deseado.

---

### Paso 4: Generar el Plan Técnico y las Tareas Atómicas
Una vez aprobada la spec, genera el plan de arquitectura y las tareas:
```text
/sdd-plan mi-nueva-feature
```
y posteriormente:
```text
/sdd-tasks mi-nueva-feature
```
> **Qué sucederá:** Se crearán los archivos `plan.md` y `tasks.md` dentro de la carpeta de la spec, desglosando la implementación en tareas atómicas (de 20–30 minutos) con sus respectivos criterios de "Hecho cuando:".

---

### Paso 5: Implementar guiado por TDD
Para comenzar a escribir código:
```text
/sdd-implement mi-nueva-feature
```
> **Qué sucederá:** El agente `implementer` tomará una tarea a la vez de `tasks.md`, creará primero la prueba unitaria/integración en rojo, escribirá el código mínimo para pasarla a verde y marcará el avance en el checkbox correspondiente.

---

### Paso 6: Validar y Auditar el Cumplimiento
Al finalizar las tareas, audita el resultado frente a la spec:
```text
/sdd-validate mi-nueva-feature
```
> **Qué sucederá:** El agente `reviewer` ejecutará la suite completa de pruebas, verificará la cobertura de los Requisitos Funcionales y entregará un veredicto final (`APROBADO` o `CAMBIOS NECESARIOS`).

---

## 🛠️ Resumen de Comandos Rápidos

| Comando | Descripción |
| :--- | :--- |
| `/sdd-constitution` | Configura el stack, reglas y comandos del proyecto. |
| `/sdd-spec [nombre]` | Crea o edita la especificación (EARS). |
| `/sdd-clarify [nombre]` | Resuelve dudas de negocio sobre la spec. |
| `/sdd-plan [nombre]` | Diseña la arquitectura y plan técnico. |
| `/sdd-tasks [nombre]` | Genera el listado de tareas atómicas. |
| `/sdd-implement [nombre]` | Ejecuta las tareas usando TDD. |
| `/sdd-validate [nombre]` | Audita el código frente a la spec y ejecuta tests. |
| `/sdd-change [nombre]` | Gestiona cambios de alcance o requerimientos. |
| `/sdd-status` | Muestra el estado actual del flujo de desarrollo. |