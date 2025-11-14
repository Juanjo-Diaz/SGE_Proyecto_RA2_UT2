```markdown
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
```


```markdown
# Instalación de Odoo en Linux — Juan José Díaz Ruiz
**Reto:** Reto_03_Instalacion_Odoo_Linux_JuanJose_DiazRuiz  
**Proyecto:** Proyecto_RA2_UT2  
**Fecha:** 2025 11 7
**Distro:** {Ubuntu 22.04 / Debian 12 / …}
```


```markdown
# Índice
1. [Requisitos previos](./02-requisitos_previos.md)
2. [Preparación del sistema](./03-preparacion_sistema.md)
3. [PostgreSQL en Linux](./04-postgresql_linux.md)
4. [Dependencias](./05-dependencias.md)
5. [Instalación de Odoo](./06-instalacion_odoo.md)
6. [Configuración de Odoo](./07-configuracion_odoo.md)
7. [Servicio systemd](./08-servicio_systemd.md)
8. [Creación de BD de prueba](./09-creacion_bd_prueba.md)
9. [Verificación de acceso](./10-verificacion.md)
10. [Problemas comunes (FAQ)](./11-troubleshooting.md)
11. [Checklist final](./12-checklist.md)
12. [Bibliografía y fuentes](./99-bibliografia.md)
```


```markdown
# 02 — Requisitos previos

- **Ubuntu/Debian** (se recomienda LTS) o tu distro equivalente.
- Usuario con permisos de **sudo**.
- **Conexión** a Internet.
- Espacio libre en disco (≥ 5–10 GB).
- (Opcional) **Git** y editor de texto (nano/vim).

> Resultado esperado: confirmas versión de distro y acceso `sudo`.
```


````markdown
# 03 — Preparación del sistema

1. Actualiza índices y paquetes:
Tienes que realizar los siguientes comandos:
```bash
sudo apt update
```
2. Tal vez sea necesario hacer algunos ajustes generales:
Ajustar el idioma del teclado o del sistema operativo.
> Resultado esperado: sistema actualizado y listo para instalar dependencias.

````


````markdown
# 04 — PostgreSQL en Linux

1. Instala PostgreSQL desde repos:
   ```bash
 sudo apt-get -y install postgresql
   ```
2. Verifica el servicio:
   ```bash
sudo -u postgres psql
SELECT version();
   ```
![](../assets/img/04-postgresql_linux/serviciopostgre.png)

> Resultado esperado: PostgreSQL instalado y activo.

````


````markdown
# 05 — Dependencias (Python, wkhtmltopdf, librerías)

1. Instala Python y paquetes de compilación:
   ```bash
   sudo apt install build-essential
   sudo apt -y install python3 python3-pip python3-venv build-essential libxslt1-dev      
   libzip-dev libldap2-dev libsasl2-dev libjpeg-dev libpq-dev
   ```
2. Instala **wkhtmltopdf** compatible (para reportes PDF).
   ```bash
   sudo dpkg -i wkhtmltox_0.12.5–1.focal_amd64.deb
   ```
3. Verifica versiones:
   ```bash
   python3 --version
   wkhtmltopdf --version
   ```
   Debería de decir lo siguiente
   ![](../assets/img/05-dependencias/pdf.png)

> Resultado esperado: dependencias instaladas y comprobadas.

````


````markdown
# 06 — Instalación de Odoo

> Elige uno de los métodos y documenta tu elección.

## Método A — Paquete oficial (repositorio Odoo)
1. Añade repositorio/clave y luego instala `odoo`:
   ```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y wget gnupg2 ca-certificates
wget -O - https://nightly.odoo.com/odoo.key | sudo gpg --dearmor -o /usr/share/keyrings/odoo-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/odoo-archive-keyring.gpg] https://nightly.odoo.com/18.0/nightly/deb/ ./" | 
  sudo tee /etc/apt/sources.list.d/odoo.list
sudo apt update
sudo apt install -y odoo
Y compruebas que se haya instalado.
sudo systemctl status odoo
![](../assets/img/06-instalacion_odoo/instalacion.png)
> Resultado esperado: binarios/código de Odoo instalados.

````


````markdown
# 07 — Configuración de Odoo (`/etc/odoo/odoo.conf`)

1. Crea/edita el archivo de configuración con:
   ```ini
   [options]
   db_host = False
   db_port = False
   db_user = odoo
   db_password = False
   addons_path = /opt/odoo/odoo-src/addons
   logfile = /var/log/odoo/odoo.log
   xmlrpc_port = 8069
   ```
2. Crea carpetas y permisos si procede:
   ```bash
   sudo mkdir -p /var/log/odoo && sudo chown odoo:odoo /var/log/odoo
   ```
   Esto es lo que deberías ver en la configuración (incluyendo la configuración del admin)
   ![](../assets/img/08-servicio_systemd/nano.png)

> Resultado esperado: configuración mínima funcional creada.

````


````markdown
# 08 — Servicio systemd (`odoo.service`)

1. Crea el servicio en `/etc/systemd/system/odoo.service`:
   ```ini
   [Unit]
   Description=Odoo Service
   After=network.target postgresql.service

   [Service]
   Type=simple
   User=odoo
   Group=odoo
   ExecStart=/opt/odoo/venv/bin/python /opt/odoo/odoo-src/odoo-bin -c /etc/odoo/odoo.conf
   Restart=on-failure

   [Install]
   WantedBy=multi-user.target
   ```
   Así debe de quedar el archivo: ![](../assets/img/08-servicio_systemd/servicio.png)
2. Recarga y arranca:
   ```bash
   sudo systemctl daemon-reload
   sudo systemctl enable --now odoo
   sudo systemctl status odoo
   ```
   ![](../assets/img/06-instalacion_odoo/instalacion.png)

![systemd](../assets/img/08-servicio_systemd/paso01_status-odoo.png "Estado de systemd")

> Resultado esperado: servicio `odoo` activo y habilitado.

````


```markdown
# 09 — Creación de base de datos de prueba

1. Accede a `http://localhost:8069`.
Para hacer esto debes de hacer un tunel de ssh con la base de datos creada, para ello usa:
![](../assets/img/09-creacion_bd_prueba/conectardb.png)
2. Crea una **base de datos nueva** con email/contraseña admin.
Para ello usa http://127.0.0.1:8069/web/database/manager y sale una pestaña donde puedes acceder a todo:
![](../assets/img/09-creacion_bd_prueba/creardb.png)

3. Selecciona módulos iniciales si procede.

![Crear BD](../assets/img/09-creacion_bd_prueba/paso01_crear-bd.png "Crear base de datos")

> Resultado esperado: BD de prueba creada y primer acceso.

```


```markdown
# 10 — Verificación de acceso

- Comprueba el **dashboard** de Odoo en el navegador.
- Captura con **fecha/hora** visibles.

![Dashboard](../assets/img/10-verificacion/paso01_dashboard.png "Panel principal Odoo")

> Resultado esperado: acceso confirmado a `localhost:8069`.

```


```markdown
# 11 — Problemas comunes (FAQ)

- **Puerto 8069 ocupado** → Cambia puerto en `odoo.conf` o libera el actual.
- **PostgreSQL no accesible** → Revisa servicio, roles y permisos.
- **wkhtmltopdf no compatible** → Instala versión recomendada para tu Odoo.
- **Permisos/propiedad** → Ajusta dueños (`odoo:odoo`) y permisos de rutas.
- **Servicio falla al arrancar** → Revisa `journalctl -u odoo` y `odoo.log`.

> Añade problemas reales encontrados y su solución con evidencia.

```


```markdown
# 12 — Checklist final

- [ ] Sistema actualizado (`apt update/upgrade`).
- [ ] PostgreSQL instalado y activo.
- [ ] Dependencias de Python/wkhtmltopdf instaladas.
- [ ] Odoo instalado (paquete o código fuente).
- [ ] `odoo.conf` creado y correcto.
- [ ] Servicio `odoo` activo (systemd).
- [ ] BD de prueba creada.
- [ ] Acceso a `http://localhost:8069` verificado.
- [ ] Capturas por sección con nombres correctos.
- [ ] Bibliografía completada (oficial + técnica).

```


```markdown
# 99 — Bibliografía y fuentes

Incluye aquí las fuentes usadas (oficiales y artículos técnicos). Ejemplos:
- Documentación oficial de Odoo (versión usada).
- Guías oficiales para Ubuntu/Debian.
- Documentación de PostgreSQL para Linux.
- Artículos técnicos (no comerciales) sobre systemd, wkhtmltopdf, etc.

> Añade **capturas con URL visible** al consultar guías online.

```
