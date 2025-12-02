# 10. Compliance Assessment – PayrollApp

## 10.1 Tipo de información

- Datos personales de empleados (PII):
  - Nombre, RFC, NSS, salario, CURP, etc.
- Documentos:
  - PDFs de recibos de nómina

## 10.2 Requisitos (simulados, pero realistas)

- Retención mínima de recibos: 5–7 años
- Acceso restringido solo a área de RRHH/autorizados
- Encriptación:
  - En tránsito (HTTPS/TLS)
  - En reposo (DB y Object Storage cifrados)
- Auditoría:
  - Saber quién consulta / modifica datos

## 10.3 Controles en OCI

- **Encriptación en reposo:**
  - Autonomous Database con TDE
  - Object Storage cifrado por defecto
- **Encriptación en tránsito:**
  - HTTPS en Load Balancer y aplicación
- **Acceso y roles (IAM):**
  - Compartment: `PAYROLL-PROD`
  - Políticas:
    - Grupo `payroll-admins`: administrar recursos de nómina
    - Grupo `payroll-readers`: sólo lectura de reportes
- **Auditoría:**
  - Habilitar y revisar OCI Audit
  - Habilitar Database Auditing en objetos sensibles

## 10.4 Riesgos y mitigaciones

- Riesgo: acceso no autorizado a PDFs de nómina
  - Mitigación: buckets privados + políticas de IAM estrictas
- Riesgo: fuga de datos en tránsito
  - Mitigación: sólo HTTPS, VPN/FastConnect para on-prem
