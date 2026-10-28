---
description: SDD · Propone o revisa los principios innegociables del proyecto en docs/constitution.md (Uso: /sdd-constitution "detalles adicionales del stack o reglas")
agent: coordinator
---
Inicia la definición o actualización de la gobernanza técnica en `docs/constitution.md`.

Instrucciones para el flujo:
1. **Inspección:** Solicita a @planner explorar la raíz del repositorio, las dependencias y la información adicional: $ARGUMENTS.
2. **Redacción de Principios:** Pide a @planner estructurar exactamente **6 principios innegociables**, claros y verificables:
   1. **Simplicidad del Stack:** Stack activo y prohibición de complejidad innecesaria.
   2. **Gobernanza de Especificación:** "Ninguna línea de código de producción existe sin una spec aprobada".
   3. **Arquitectura y Modularidad:** Separación entre lógica de negocio y capa de presentación.
   4. **Política de Tests (TDD):** Framework obligatorio y comando oficial de pruebas.
   5. **Seguridad y Protección de Datos:** Cifrado, secretos y privacidad.
   6. **Convenio de Idioma y Estilo:** Idioma para código, commits, docs y UI.
3. **Presentación:** Muestra la propuesta al usuario en consola y **PARÁ** a la espera de su confirmación explícita.
4. **Guardado:** Una vez aprobada por el usuario, delega el guardado final en `docs/constitution.md`.