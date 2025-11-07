# 04 — PostgreSQL en Linux

1. Instala PostgreSQL desde repos:
   ```bash
   sudo apt -y install postgresql
   ```
2. Verifica el servicio:
   ```bash
   sudo systemctl status postgresql
   ```
   ![Servicio PostgreSQL](../assets/img/04-postgresql_linux/paso01_status-postgres.png "Estado del servicio")

3. (Opcional) Cambia contraseña del usuario `postgres` o crea rol específico para Odoo.

> Resultado esperado: PostgreSQL instalado y activo.
