# 5. Source Discovery – PayrollApp

## 5.1 Inventario de VMs

| Hostname   | IP          | Rol   | OS    | vCPU | RAM  | Disco | Notas                      |
|------------|------------|-------|-------|------|------|-------|----------------------------|
| app01      | 10.10.10.11| App   | Linux | 4    | 16GB | 200GB | WebLogic/Tomcat            |
| app02      | 10.10.10.12| App   | Linux | 4    | 16GB | 200GB | WebLogic/Tomcat            |
| db01       | 10.10.20.10| DB    | Linux | 8    | 64GB | 2TB   | Oracle DB 19c              |
| nas01      | 10.10.30.10| Files | N/A   | N/A  | N/A  | 1TB   | NFS con PDFs de nómina     |

## 5.2 Dependencias identificadas

- App Servers → DB Server
  - Protocolo: TCP
  - Puerto: 1521 (Oracle)
- App Servers → LDAP
  - Autenticación de usuarios corporativos
- App Servers → SMTP
  - Envío de correos de notificación de nómina
- App Servers → NAS
  - Montaje NFS para leer y escribir PDFs

## 5.3 Notas de descubrimiento

- Validar versiones de Java y aplicación
- Confirmar tamaño de tablas críticas en la DB
- Confirmar volumen de nuevos PDFs por mes (crecimiento)
