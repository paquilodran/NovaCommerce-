# Arquitectura

## Visión general

La infraestructura se diseñará siguiendo una arquitectura de tres capas.
<img width="816" height="623" alt="image" src="https://github.com/user-attachments/assets/fe4e3882-ae52-412e-947a-4ac041c02b3e" />


---

# Capas

## Networking

Responsable de la comunicación.

Incluye:

- VPC
- Internet Gateway
- NAT Gateway
- Route Tables
- Subredes

---

## Compute

Encargada de ejecutar la aplicación.

Componentes:

- EC2
- Launch Template
- Auto Scaling Group

---

## Data

Persistencia.

Incluye:

- PostgreSQL
- Backups

---

## Storage

Almacenamiento de imágenes.

Amazon S3.

---

## Monitoring

CloudWatch.

Alarmas.

Logs.

Métricas.

---

## Seguridad

IAM

Security Groups

Least Privilege
