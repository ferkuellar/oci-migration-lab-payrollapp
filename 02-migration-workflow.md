# 2. Migration Workflow – PayrollApp

## 2.1 Fases principales

1. Descubrimiento e inventario (Discovery)
2. Assessment (App, Compute, Storage, Network, Compliance)
3. Diseño de la arquitectura objetivo en OCI
4. Migración técnica (PoC → Piloto → Producción)
5. Cutover y optimización

## 2.2 Diagrama lógico (alto nivel)

On-Prem  →  Descubrimiento  →  Assessment  →  Diseño OCI  →  PoC  →  Piloto  →  Producción

## 2.3 Tareas clave por fase

### 1) Descubrimiento
- Inventario de VMs (CPU, RAM, OS, IP)
- Identificar aplicaciones y dependencias (DB, LDAP, SMTP, etc.)
- Medir uso de CPU, RAM y almacenamiento (aunque sea estimado)

### 2) Assessment
- Clasificar criticidad de la app (alta, media, baja)
- Evaluar necesidades de cómputo y crecimiento
- Evaluar tamaño y tipo de datos (DB + archivos)
- Evaluar requisitos de red, seguridad y compliance

### 3) Diseño de destino en OCI
- Seleccionar región y compartment
- Diseñar VCN y subredes (app, db, bastion)
- Elegir servicios: Compute, DB System/Autonomous, Object Storage
- Definir conectividad on-prem ↔ OCI (VPN/FastConnect)

### 4) Migración técnica
- Configurar networking (VCN, DRG, VPN)
- Preparar migración de DB (RMAN/Data Pump/servicios de migración)
- Preparar migración de archivos a Object Storage
- Desplegar VMs/app en OCI

### 5) Cutover y optimización
- Plan de cambio y ventana de mantenimiento
- Validaciones funcionales (login, cálculo y consulta de nómina)
- Ajuste de recursos (vertical/horizontal)
- Activar monitoreo y alertas
