## Introducción

Este documento registra las decisiones de arquitectura tomadas durante el diseño de la infraestructura de NovaCommerce.

Cada decisión busca resolver un problema específico del proyecto y deja documentado el contexto, la decisión adoptada y sus consecuencias.

Documentar estas decisiones facilita el mantenimiento del proyecto, mejora la comunicación entre equipos y permite comprender el motivo detrás de cada elección técnica.

---

# ADR-001 — Uso de Terraform como Infrastructure as Code

## Estado

✅ Aprobado

## Contexto

La infraestructura inicial de NovaCommerce era administrada manualmente desde la consola de AWS. Esto generaba configuraciones inconsistentes, dificultaba la reproducción de ambientes y aumentaba el riesgo de errores humanos.

## Decisión

Toda la infraestructura será administrada mediante Terraform.

Terraform será la única fuente de verdad para la creación, modificación y eliminación de recursos en AWS.

## Consecuencias

### Positivas

- Infraestructura versionada.
- Despliegues repetibles.
- Automatización.
- Reducción de errores humanos.
- Facilidad para trabajar en equipo.

### Negativas

- Curva de aprendizaje inicial.
- Mayor planificación antes de implementar cambios.

---

# ADR-002 — Uso de Amazon Web Services (AWS)

## Estado

✅ Aprobado

## Contexto

El proyecto requiere una plataforma cloud ampliamente utilizada por empresas y compatible con Terraform.

## Decisión

Se utilizará Amazon Web Services como proveedor de nube.

## Justificación

AWS ofrece una amplia variedad de servicios administrados, alta disponibilidad, escalabilidad y una excelente integración con Terraform.

## Consecuencias

### Positivas

- Amplia documentación.
- Escalabilidad.
- Servicios administrados.
- Integración con herramientas DevOps.

### Negativas

- Costos variables.
- Gran cantidad de servicios disponibles, lo que incrementa la complejidad.

---

# ADR-003 — Arquitectura Modular

## Estado

✅ Aprobado

## Contexto

La infraestructura crecerá progresivamente y será necesario mantener el código organizado.

## Decisión

Cada componente de infraestructura será implementado como un módulo independiente de Terraform.

Ejemplos:

- VPC
- IAM
- Security Groups
- EC2
- RDS
- S3
- CloudWatch

## Consecuencias

### Positivas

- Código reutilizable.
- Fácil mantenimiento.
- Mejor organización.
- Escalabilidad.

### Negativas

- Mayor cantidad de archivos.
- Mayor planificación inicial.

---

# ADR-004 — Base de Datos PostgreSQL

## Estado

✅ Aprobado

## Contexto

NovaCommerce necesita almacenar información transaccional como usuarios, pedidos, productos e inventario.

## Decisión

La base de datos será Amazon RDS PostgreSQL.

## Justificación

PostgreSQL es una base de datos relacional robusta, ampliamente utilizada y totalmente compatible con Amazon RDS.

## Consecuencias

### Positivas

- Alta confiabilidad.
- Backups administrados.
- Integración con AWS.

### Negativas

- Mayor costo que una base de datos autoadministrada.

---

# ADR-005 — Separación por Ambientes

## Estado

✅ Aprobado

## Contexto

Los cambios de infraestructura deben validarse antes de llegar a producción.

## Decisión

El proyecto utilizará tres ambientes independientes:

- Development
- Staging
- Production

Cada ambiente tendrá su propia configuración y archivos de variables.

## Consecuencias

### Positivas

- Menor riesgo.
- Validación previa de cambios.
- Mejor organización.

### Negativas

- Mayor cantidad de recursos.
- Mayor administración.

---

# ADR-006 — Control de Versiones

## Estado

✅ Aprobado

## Contexto

Toda modificación sobre la infraestructura debe quedar registrada.

## Decisión

El repositorio será administrado mediante Git y alojado en GitHub.

## Consecuencias

### Positivas

- Historial de cambios.
- Colaboración.
- Integración futura con GitHub Actions.

### Negativas

- Requiere seguir buenas prácticas de versionado.

---

# Próximas decisiones

A medida que avance el proyecto se incorporarán nuevos ADR relacionados con:

- Backend remoto de Terraform.
- Estrategia de monitoreo.
- Gestión de secretos.
- Auto Scaling.
- Alta disponibilidad.
- CI/CD.
