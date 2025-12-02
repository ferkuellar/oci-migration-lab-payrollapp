# 4. On-Prem Topology – PayrollApp

## 4.1 Red on-prem (simplificada)

- Subred App: 10.10.10.0/24
- Subred DB:  10.10.20.0/24
- Firewall perimetral con salida a Internet
- Usuarios acceden vía HTTPS a PayrollApp

## 4.2 Servidores

- App Server 1
  - IP: 10.10.10.11
  - OS: Linux
  - CPU/RAM: 4 vCPU, 16 GB
- App Server 2
  - IP: 10.10.10.12
  - OS: Linux
  - CPU/RAM: 4 vCPU, 16 GB
- DB Server
  - IP: 10.10.20.10
  - OS: Linux
  - CPU/RAM: 8 vCPU, 64 GB
  - Disco: 2 TB (LUN iSCSI)

## 4.3 Almacenamiento

- NAS (NFS)
  - Capacidad: 1 TB
  - Uso: PDFs de recibos de nómina (~500 GB usados)

## 4.4 Diagrama textual

Usuarios → Internet → Firewall → LAN  
LAN → Subred App (2 VMs)  
LAN → Subred DB (1 VM)  
LAN → NAS (NFS con PDFs)
