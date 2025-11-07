# Reto 3 — Instalación de Odoo en **Linux** (Manual + capturas)

**Objetivo**: Documentar **paso a paso** cómo descargar, instalar, configurar y **ejecutar Odoo** en Linux (se recomienda **Ubuntu/Debian**).  
Incluye **capturas** de cada etapa y una **bibliografía** (documentación oficial y recursos técnicos) que hayas seguido.

> Si usas otra distro (Fedora, Rocky, Arch…), indícalo y adapta los comandos.

## Entregable
- Carpeta completa de este reto con:
  - `docs/` → secciones numeradas (00–11 + 99).
  - `assets/img/<NN-seccion>/` → capturas con nombres `pasoNN_descripcion-kebab.png`.
  - `rubric/R03_Instalacion_Odoo_Linux_rubrica.md` → rúbrica para auto-revisión.

## Índice sugerido (en `docs/01-indice.md`)
1. Portada → `00-portada.md`
2. Índice → `01-indice.md`
3. Requisitos previos → `02-requisitos_previos.md`
4. Preparación del sistema (update/paquetes) → `03-preparacion_sistema.md`
5. PostgreSQL en Linux → `04-postgresql_linux.md`
6. Dependencias (Python, wkhtmltopdf, libs) → `05-dependencias.md`
7. Instalación de Odoo (paquete oficial o desde código) → `06-instalacion_odoo.md`
8. Configuración (`/etc/odoo/odoo.conf`) → `07-configuracion_odoo.md`
9. Servicio systemd (`odoo.service`) → `08-servicio_systemd.md`
10. Creación de BD de prueba → `09-creacion_bd_prueba.md`
11. Verificación de acceso → `10-verificacion.md`
12. Problemas comunes (FAQ) → `11-troubleshooting.md`
13. Checklist final → `12-checklist.md`
14. Bibliografía y fuentes → `99-bibliografia.md`

> Usa **enlaces relativos** a imágenes:  
> `![Texto alternativo](../assets/img/03-preparacion_sistema/paso01_update-upgrade.png "Update/Upgrade")`
