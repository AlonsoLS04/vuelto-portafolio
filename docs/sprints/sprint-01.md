# Sprint 1 — MVP: registrar un gasto desde una foto en Telegram

- **Fecha:** 2026-10-24
- **Objetivo:** enviar la foto de un comprobante a un bot de Telegram y que quede una fila correcta en Google Sheets.
- **Versión:** v0.1.0
- **Resultado:** ✅ Objetivo cumplido

## Historias completadas
HU-1.1 a HU-1.5 · HU-2.1 a HU-2.4 · HU-3.1 a HU-3.4 · HU-4.1 · HU-4.2 · HU-8.1
(detalle en el [Product Backlog](../product_backlog.md))

## Incremento entregado
| Componente | Qué hace |
|-----------|----------|
| `bot.py` | Bot con `python-telegram-bot`: fotos, texto rápido, botones, correcciones y comandos `/resumen`, `/ultimos`, `/deshacer`, `/hoja` |
| `extractor.py` | Envía la imagen a Gemini (o Claude), normaliza montos y fechas peruanas y devuelve un borrador limpio |
| `sheets.py` | Crea la pestaña **Movimientos** con encabezados y escribe fechas y montos tipados para Power BI |
| `README.md` | Guía de instalación paso a paso y medidas DAX de partida |

## Evidencia
Fechas de creación de `README.md`, `.env.example`, `requirements.txt` (19:42), `sheets.py` (20:54),
`extractor.py` (21:13) y `bot.py` (22:05) del 2026-10-24.

## Decisiones técnicas
- [ADR-001](../decisiones/ADR-001-telegram-como-canal.md) Telegram como canal de captura
- [ADR-002](../decisiones/ADR-002-google-sheets-como-fuente-unica.md) Google Sheets como fuente única
- [ADR-003](../decisiones/ADR-003-extractor-gemini-con-alternativa-claude.md) Gemini con alternativa Claude

## Retrospectiva (lecciones aprendidas, escritas el 2026-11-07)
- ✅ **Funcionó:** empezar por el flujo más corto de valor (foto → fila) y dejar la corrección en manos del usuario antes de guardar.
- ✅ **Funcionó:** diseñar la hoja pensando en Power BI desde el día 1 (fecha y monto tipados, monto siempre positivo + columna Tipo).
- ⚠️ **Mejorar:** el código no se versionó en git desde el inicio (ver DT-2).
- ⚠️ **Mejorar:** sin casos de prueba para `parse_amount` y `parse_date`, que es donde más se equivoca un lector de vouchers.
