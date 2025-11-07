# 05 — Integración con Gmail (OAuth GCP + Add-on)

> Estructura orientativa

## Requisitos
- Cuenta Google Cloud (GCP).

## Pasos resumidos
1. **Activar plugin de correo** en Odoo e instalar *Odoo Inbox Add-on* en Gmail.
2. En **Google Cloud Console**: habilitar *Gmail API*, crear **OAuth Client (Web)**, configurar **redirect URI** de Odoo.
3. Copiar **Client ID/Secret** a Odoo (Gmail server settings) y **Guardar**.
4. Probar desde Gmail: crear contacto/oportunidad desde el add-on.

![GCP OAuth](../assets/img/05-integracion_gmail/paso01_gcp-oauth.png "GCP OAuth")
