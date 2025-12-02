# 3. Migration Scenarios – PayrollApp

## 3.1 Escenarios posibles

- **Rehost (Lift-and-Shift)**  
  Mover las VMs casi tal cual a OCI (Compute u OCVS).

- **Replatform**  
  Cambiar solo la capa de infraestructura (por ejemplo, base de datos a Autonomous).

- **Refactor / Modernizar**  
  Rediseñar la aplicación a microservicios / contenedores (OKE).

## 3.2 Decisión para PayrollApp (Fase 1)

- App:
  - Estrategia: **Rehost**
  - Motivo: minimizar cambios de código y riesgo inicial.
- Base de datos:
  - Estrategia: **Replatform**
  - Migrar a Autonomous / DB System.

- Archivos PDF:
  - Estrategia: **Replatform**
  - Mover de NAS on-prem a Object Storage.

## 3.3 Fase futura (modernización)

- Objetivo: mover la app a contenedores (OKE) o servicios más cloud-native.
- Momento: después de estabilizar la operación en OCI.
