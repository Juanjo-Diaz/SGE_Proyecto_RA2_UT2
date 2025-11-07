# Rúbrica — Reto 3: Instalación de Odoo en Linux (24 puntos)

Puntúa cada criterio con **0, 1 o 2 puntos**. Máximo: **24 puntos**.

| Criterio | 0 puntos | 1 punto | 2 puntos |
|---|---|---|---|
| Estructura del reto | Estructura incompleta o desordenada. | Falta algún elemento menor. | Estructura exacta: `docs/`, `assets/img/<NN-seccion>/`, `rubric/`, `README.md`. |
| Índice y navegación | Sin índice o enlaces rotos. | Índice presente con enlaces mejorables. | `01-indice.md` operativo y enlaces relativos correctos entre secciones. |
| Requisitos previos | No identifica prerrequisitos. | Requisitos incompletos o genéricos. | Requisitos claros (distro, sudo, espacio, etc.). |
| Preparación del sistema | Pasos confusos o sin capturas. | Pasos presentes con omisiones. | Update/upgrade y ajustes documentados con evidencia. |
| PostgreSQL | No documentado. | Documentado parcialmente. | Instalación/verificación con evidencia. |
| Dependencias | No documentado. | Documentado parcialmente. | Python/wkhtmltopdf/libs instaladas y validadas. |
| Instalación de Odoo | Ausente/ambiguo. | Parcial (un método sin detalle). | Método elegido (paquete o fuente) claro y reproducible. |
| Configuración + Servicio | Sin `odoo.conf` o sin systemd. | Uno de los dos incompleto. | `odoo.conf` correcto + `systemd` activo y verificado. |
| BD de prueba + Verificación | Sin BD o sin pruebas. | BD creada o verificación mínima. | BD creada y acceso a `localhost:8069` con dashboard (fecha/hora). |
| Troubleshooting | Ausente. | Pocos casos genéricos. | Casos reales + soluciones con evidencia. |
| Capturas (nombres/rutas) | Rutas rotas/nombres erróneos. | Alguna inconsistencia menor. | `assets/img/<NN-seccion>/pasoNN_descripcion-kebab.png` correcto. |
| Redacción + Bibliografía | Redacción deficiente y/o sin fuentes. | Clara pero con citas mejorables. | Clara, concisa y técnica; mayoría de fuentes oficiales/técnicas. |
| Entrega en PDF único | No hay PDF único o faltan apartados clave. | PDF con faltas menores o formato mejorable. | PDF consolidado con todos los apartados y buen formato. |

**Puntos de corte sugeridos**: 21–24 (Sobresaliente), 17–20 (Notable), 12–16 (Aprobado), <12 (Suspenso).
