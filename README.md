# OCI Migration Lab – PayrollApp (On-Prem → OCI)

Laboratorio práctico para simular la migración de una aplicación de nómina (**PayrollApp**) desde un data center on-premises hacia **Oracle Cloud Infrastructure (OCI)**, siguiendo la mentalidad y el contenido de la certificación **Oracle Cloud Infrastructure Migration Architect Professional**.

Este repo no contiene código de la app, sino algo igual o más importante para un arquitecto:  
el **análisis completo de la migración** (fundamentos, escenarios, assessments, red, seguridad, compliance).

---

## Objetivo del laboratorio

Practicar el **proceso completo de migración** de un workload empresarial:

- Entender el entorno **on-prem** (app, base de datos, almacenamiento, red)
- Elegir el **escenario de migración** (rehost, replatform, refactor)
- Diseñar la **arquitectura objetivo en OCI**
- Evaluar **compute, storage, red, seguridad y compliance**
- Documentar todo como lo haría un **Migration Architect** en un proyecto real

Todo está pensado para alguien que está *estudiando la certificación* y quiere algo entre  
“laboratorio guiado” y “proyecto para portafolio”.

---

## Escenario simulado: PayrollApp

**PayrollApp** es una aplicación interna de nómina que corre on-premises:

- 2 VMs de aplicación (Java + WebLogic/Tomcat)
- 1 VM con **Oracle Database 19c** (~1.2 TB)
- 1 NAS con ~500 GB de PDFs de recibos de nómina
- Usuarios internos acceden vía HTTPS
- La app usa LDAP, SMTP y acceso a archivos en NAS

El objetivo es migrar este entorno a OCI, con una primera fase de **lift-and-shift / replatform** y una futura fase de modernización.

---

## Estructura del repositorio

Todo el análisis está en la carpeta `docs/`:

```text
docs/
├─ 01-migration-fundamentals.md
├─ 02-migration-workflow.md
├─ 03-migration-scenarios.md
├─ 04-onprem-topology.md
├─ 05-source-discovery.md
├─ 06-app-assessment.md
├─ 07-compute-assessment.md
├─ 08-storage-data-assessment.md
├─ 09-network-security.md
└─ 10-compliance-assessment.md
