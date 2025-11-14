# 06 — Instalación de Odoo

> Elige uno de los métodos y documenta tu elección.

## Método A — Paquete oficial (repositorio Odoo)
1. Añade repositorio/clave y luego instala `odoo`:
   ```bash
   # (Ejemplo orientativo — ajusta a la versión que uses)
   sudo apt -y install odoo
   ```

## Método B — Desde código fuente (git)
1. Crea usuario del sistema `odoo` (sin shell de login si prefieres):
   ```bash
   sudo useradd -m -d /opt/odoo -U -r -s /bin/bash odoo
   ```
2. Clona código y crea entorno virtual:
   ```bash
   sudo -u odoo -H bash -c 'git clone https://github.com/odoo/odoo.git /opt/odoo/odoo-src -b <version>'
   sudo -u odoo -H bash -c 'python3 -m venv /opt/odoo/venv && /opt/odoo/venv/bin/pip install -U pip wheel'
   sudo -u odoo -H bash -c '/opt/odoo/venv/bin/pip install -r /opt/odoo/odoo-src/requirements.txt'
   ```

> Resultado esperado: binarios/código de Odoo instalados.
