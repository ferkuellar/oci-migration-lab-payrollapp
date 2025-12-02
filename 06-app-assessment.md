# 6. Application Assessment – PayrollApp

## 6.1 Características de la aplicación

- Tipo: Aplicación web de nómina (PayrollApp)
- Tecnología: Java + WebLogic/Tomcat
- Estado: **Stateful** (mantiene sesión de usuario)
- Autenticación: LDAP corporativo
- Dependencia fuerte de la base de datos (Oracle)

## 6.2 Criticidad

- Impacto si falla:
  - Alto: afecta pago de nómina a empleados
- Ventana de mantenimiento permitida:
  - Ejemplo: sábado de 02:00 a 06:00 AM (4 horas)

## 6.3 Requisitos no funcionales

- Disponibilidad objetivo: 99.9%
- Número de usuarios concurrentes: ~200
- Picos de carga: fin de mes y quincenas

## 6.4 Riesgos de migración

- Compatibilidad de versiones de Java/app con nuevo entorno
- Latencia adicional si la DB sigue on-prem (no deseable)
- Problemas de certificados SSL en el nuevo dominio
- Configuración de LDAP y SMTP en OCI

## 6.5 Plan mínimo de pruebas post-migración

- Usuarios pueden iniciar sesión correctamente
- Consultar históricos de recibos de nómina
- Generar una nómina de prueba
- Descargar PDFs sin errores
