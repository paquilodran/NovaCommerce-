# 03. Arquitectura

## Arquitectura objetivo

```text
Internet
     │
Route53
     │
Application Load Balancer
     │
Auto Scaling Group
     │
EC2
     │
RDS PostgreSQL

S3
CloudWatch
IAM
VPC
```

---

# Componentes

## VPC

Red principal de la infraestructura.

## Public Subnets

Alojan los recursos públicos.

## Private Subnets

Protegen servicios internos.

## EC2

Servidores de aplicación.

## RDS

Base de datos PostgreSQL.

## S3

Almacenamiento de archivos.

## CloudWatch

Monitoreo.

## IAM

Gestión de permisos.

---

# Principios

- Seguridad
- Escalabilidad
- Modularidad
- Reutilización
- Automatización
