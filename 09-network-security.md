# 9. Network & Security – PayrollApp

## 9.1 Diseño VCN

- VCN: `payroll-vcn` – 10.0.0.0/16

Subredes:
- `payroll-public-subnet`  – 10.0.1.0/24 (bastion / LB)
- `payroll-app-subnet`     – 10.0.10.0/24 (app servers)
- `payroll-db-subnet`      – 10.0.20.0/24 (base de datos)

## 9.2 Conectividad on-prem ↔ OCI

- Opción recomendada: IPSec VPN
  - On-prem Router/Firewall ↔ OCI DRG ↔ VCN
- Opcional para grandes volúmenes: FastConnect

## 9.3 Reglas de seguridad (ejemplo conceptual)

- App Subnet:
  - Permitir HTTPS (443) desde Internet (o solo desde LB)
  - Permitir SSH (22) solo desde bastion/VPN
- DB Subnet:
  - Permitir puerto DB (1521) SOLO desde App Subnet
  - Sin acceso directo desde Internet

## 9.4 Notas de seguridad

- Usar NSGs para agrupar reglas por rol (App, DB)
- Deshabilitar todo tráfico entrante por defecto
- Encriptar tráfico con TLS (HTTPS)

## 9.5 Tarea en la consola OCI (simple, para aprender)

1. Entra a tu Consola OCI.

2. Ve a Networking → Virtual Cloud Networks.

3. Crea una VCN nueva:

  - Nombre: payroll-vcn

  - IDR: 10.0.0.0/16

4. Crea 3 subredes (aunque no lances VMs todavía), usando los CIDR de arriba.

5. Explora cómo OCI te deja definir Security Lists y Route Tables.
