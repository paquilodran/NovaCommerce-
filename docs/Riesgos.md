# 06. Análisis de Riesgos

## Objetivo

Identificar los principales riesgos asociados al diseño e implementación de la infraestructura de NovaCommerce y definir estrategias para reducir su impacto.

---

## Riesgo 1 – Eliminación accidental de infraestructura

### Impacto
Alto

### Probabilidad
Media

### Mitigación

- Revisar siempre `terraform plan`.
- Evitar ejecutar `terraform destroy` sobre producción.
- Mantener el código versionado en Git.

---

## Riesgo 2 – Costos inesperados en AWS

### Impacto
Alto

### Probabilidad
Media

### Mitigación

- Utilizar instancias pequeñas durante el desarrollo.
- Eliminar recursos cuando no estén en uso.
- Monitorear costos desde AWS.

---

## Riesgo 3 – Exposición de recursos públicos

### Impacto
Muy alto

### Mitigación

- Security Groups restrictivos.
- Principio de mínimo privilegio.
- Recursos sensibles en subredes privadas.

---

## Riesgo 4 – Pérdida del estado de Terraform

### Mitigación

Backend remoto utilizando:

- Amazon S3
- DynamoDB (State Lock)

---

## Riesgo 5 – Cambios sin revisión

### Mitigación

- Pull Requests
- Revisión de código
- Terraform Plan antes del Apply
