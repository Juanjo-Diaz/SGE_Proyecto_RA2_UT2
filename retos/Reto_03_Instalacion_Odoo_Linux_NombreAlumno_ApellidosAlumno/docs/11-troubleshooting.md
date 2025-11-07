# 11 — Problemas comunes (FAQ)

- **Puerto 8069 ocupado** → Cambia puerto en `odoo.conf` o libera el actual.
- **PostgreSQL no accesible** → Revisa servicio, roles y permisos.
- **wkhtmltopdf no compatible** → Instala versión recomendada para tu Odoo.
- **Permisos/propiedad** → Ajusta dueños (`odoo:odoo`) y permisos de rutas.
- **Servicio falla al arrancar** → Revisa `journalctl -u odoo` y `odoo.log`.

> Añade problemas reales encontrados y su solución con evidencia.
