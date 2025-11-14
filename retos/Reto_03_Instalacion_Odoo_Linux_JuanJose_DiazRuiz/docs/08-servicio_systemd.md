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
