---
description: SDD · Propone o revisa los principios innegociables del proyecto en docs/constitution.md (Uso: /sdd-constitution "detalles adicionales del stack o reglas")
agent: planner
---
Crea o revisa el archivo de gobernanza técnica `docs/constitution.md` aplicando la skill sdd.

Instrucciones:
1. **Inspección de Entorno:** Explora la raíz del proyecto (archivos de configuración de dependencias, estructura de carpetas) y lee `AGENTS.md` y `MEMORY.md` para identificar el stack tecnológico real del repositorio.
2. **Contexto Adicional:** Considera la información adicional proporcionada por el usuario: $ARGUMENTS
3. Propón exactamente **6 principios innegociables**, cortos, claros y verificables objetivamente, que abarquen:
   1. **Simplicidad del Stack:** Definición del stack tecnológico activo (frameworks, base de datos) y prohibición de complejidad innecesaria.
   2. **Gobernanza de Especificación:** Relación estricta entre la spec y el código ("Ninguna línea de código de producción existe sin una spec aprobada").
   3. **Arquitectura y Modularidad:** Separación clara entre la lógica de negocio y las capas de presentación/interfaz.
   4. **Política de Tests (TDD):** Elección del marco de pruebas (testing framework) obligatorio y el comando ejecutor oficial de la suite.
   5. **Seguridad y Protección de Datos:** Cifrado, manejo de credenciales, secretos y privacidad.
   6. **Convenio de Idioma y Estilo:** Idioma oficial para código fuente, comentarios, commits, documentación y la interfaz de usuario (UI).

Reglas de entrega:
- **NO modifiques `docs/constitution.md` todavía:** muestra únicamente la propuesta en consola en un formato conciso.
- Espera la confirmación o ajustes del usuario antes de guardar el archivo.