# 1. Migration Fundamentals – PayrollApp

## 1.1 Descripción del sistema origen (on-prem)

- Aplicación: **PayrollApp** (nómina)
- App Servers:
  - 2 VMs Linux
  - 4 vCPU, 16 GB RAM cada una
  - Java + WebLogic/Tomcat
- Base de Datos:
  - 1 VM Linux
  - 8 vCPU, 64 GB RAM
  - Oracle Database 19c
  - 2 TB de almacenamiento
- Archivos:
  - NAS/NFS con ~500 GB de PDFs de recibos de nómina

## 1.2 Motivos de la migración

- Reducir costos de hardware on-prem
- Mejorar disponibilidad y recuperación ante desastres
- Aumentar seguridad y trazabilidad de accesos
- Escalar recursos bajo demanda (OCPUs / almacenamiento)

## 1.3 Objetivos de alto nivel

- Migrar la base de datos a un servicio administrado en OCI (DB System o Autonomous)
- Migrar la aplicación con un enfoque inicial de **lift-and-shift**
- Mover los PDFs a **OCI Object Storage**
- Definir una arquitectura que respete seguridad y compliance de datos de nómina
