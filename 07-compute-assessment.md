# 7. Compute Assessment – PayrollApp

## 7.1 Recursos actuales (estimados)

### App Servers (app01, app02)
- 4 vCPU, 16 GB RAM cada uno
- Uso promedio CPU: ~40%
- Uso RAM: ~60%

### DB Server (db01)
- 8 vCPU, 64 GB RAM
- Uso promedio CPU: ~60%
- Uso RAM: ~70%

## 7.2 Propuesta en OCI

### App

- 2 instancias:
  - Shape: VM.Standard3.Flex
  - 2 OCPUs, 16 GB RAM cada una
  - Motivo:
    - Reducir OCPUs (40% uso on-prem)
    - Mantener memoria igual por seguridad
    - Shape flexible permite ajustar OCPUs después

### Base de Datos

- Opción A: DB System (Oracle Database en OCI)
- Opción B: Autonomous Transaction Processing (ATP)
- Decisión (para el lab): Autonomous
  - Menos administración
  - Escalado más sencillo
  - Seguridad y parches automatizados

## 7.3 Consideraciones de alta disponibilidad

- Ubicar VMs de app en diferentes AD/Fault Domains
- Usar al menos 2 instancias de app detrás de un Load Balancer
- Evaluar multi-AD/región en fases avanzadas
