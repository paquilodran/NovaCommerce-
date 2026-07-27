# Arquitectura

## Visión general

La infraestructura se diseñará siguiendo una arquitectura de tres capas.

```text
                     Internet
                         │
                    Route53
                         │
                    ACM (HTTPS)
                         │
            Application Load Balancer
                         │
                Auto Scaling Group
                 EC2 Amazon Linux
                         │
              Spring Boot REST API
                         │
                  RDS PostgreSQL

────────────────────────────────────────

S3 → Imágenes

CloudWatch → Logs

IAM → Seguridad

VPC

Public Subnets

Private Subnets

NAT Gateway

Terraform Backend
(S3 + DynamoDB)
```

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
