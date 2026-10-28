---
description: SDD · Entrevista al usuario y redacta la spec inicial en borrador (Uso: /sdd-spec 001-nombre-feature "Descripción inicial de la idea")
agent: coordinator
---
Inicia la fase 1 (Spec) para la especificación ubicada en `specs/$1/`.

Contexto e idea inicial: $ARGUMENTS

Instrucciones obligatorias para el flujo:
1. **Entrevista / Clarificación:** Solicita a @planner analizar la idea. Si existen ambigüedades de negocio, presenta una lista numerada con un máximo de 5 preguntas de clarificación al usuario y **PARÁ** a la espera de las respuestas.
2. **Redacción de Spec:** Con la información completa, pide a @planner crear `specs/$1/spec.md`:
   - Estado: `borrador`.
   - Requisitos Funcionales (RF) estructurados en formato EARS.
   - Enfoque exclusivo en el **QUÉ y POR QUÉ** (prohibido incluir stack, arquitectura o nombres de archivos).
3. **Auditoría QA Previa:** Una vez creada la spec, llama automáticamente a @reviewer para validar si existen ambigüedades técnicas, contradicciones o casos límite omitidos.
4. **Presentación:** Muestra el borrador y el reporte inicial de QA al usuario, y solicita su aprobación explícita para pasar a la fase de Plan.