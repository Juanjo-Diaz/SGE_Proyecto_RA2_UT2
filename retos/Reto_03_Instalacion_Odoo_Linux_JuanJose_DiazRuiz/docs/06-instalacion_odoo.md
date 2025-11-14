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

> Resultado esperado: binarios/código de Odoo instalados.
