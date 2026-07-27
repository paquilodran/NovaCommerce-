# Requisitos

## Funcionales

La plataforma deberá permitir:

- Hospedar una API REST.
- Ejecutar servidores de aplicación.
- Almacenar imágenes de productos.
- Disponer de una base de datos PostgreSQL.
- Balancear tráfico HTTP/HTTPS.
- Registrar logs.
- Monitorear recursos.

---

# No funcionales

La infraestructura deberá cumplir con:

- Alta disponibilidad.
- Escalabilidad horizontal.
- Seguridad por defecto.
- Bajo costo operativo.
- Automatización.
- Versionamiento.

---

# Restricciones

El proyecto será desplegado utilizando AWS Academy.

Por este motivo:

- Se minimizará el costo.
- Se evitarán servicios innecesarios.
- Se destruirán recursos cuando no estén en uso.

---

# Ambientes

El proyecto contemplará tres ambientes.

- Development
- Staging
- Production

Cada uno tendrá configuraciones independientes.
