# Sprint 3 — App web conectada a la misma hoja

- **Fechas:** 2026-11-06 → 2026-11-07
- **Objetivo:** tener una app web privada, usable desde el iPhone, que lea y escriba en la misma hoja que el bot.
- **Versión:** v0.3.0 (commit `28fa0d9` — "styleguide y foto de voucher")
- **Resultado:** ✅ Objetivo cumplido

## Historias completadas
HU-4.3 · HU-5.4 · HU-6.1 a HU-6.7 · HU-7.1 a HU-7.4 · HU-8.2 · HU-8.3

## Cómo avanzó el sprint
| Paso | Evidencia | Resultado |
|------|-----------|-----------|
| 1. Especificación funcional | `SPEC.md` (2026-11-06 23:52) | Principios de producto, modelo de datos, pantallas y adaptación al ecosistema peruano (Yape, Plin, bancos) |
| 2. Prototipo local | `src/lib/*` (parsers, clasificador, presupuesto, recurrentes) | App React funcionando con datos de demo en el navegador |
| 3. Conexión a Google Sheets + foto | Carpeta `vuelto-foto` (2026-11-07 00:34) | Servidor Express con login; la web lee/escribe **gastos** en la hoja y lee vouchers con Gemini |
| 4. Repositorio en GitHub y Railway | `reset: moving to origin/main` (02:03) | Servicio web desplegado junto al bot |
| 5. Rediseño del inicio | commit `54dbe52` "rediseño inicio" (02:14) | |
| 6. Guía de estilos y foto de voucher | commit `28fa0d9` (02:32) | Ícono para iPhone, `index.css` con la guía de estilos |

## Decisiones técnicas
- [ADR-005](../decisiones/ADR-005-web-react-express-mismo-servidor.md) React + Express en un solo servicio con login por contraseña
- [ADR-006](../decisiones/ADR-006-pwa-en-lugar-de-app-nativa.md) Web "agregar a inicio" en lugar de app nativa
- [ADR-007](../decisiones/ADR-007-configuracion-web-en-pestana-webconfig.md) Configuración de la web en la pestaña `WebConfig`

## Fuera del sprint (pasa al backlog)
- La web solo manejaba **gastos**; los ingresos registrados por Telegram se respetaban pero no se mostraban → Sprint 4.

## Retrospectiva (lecciones aprendidas, escritas el 2026-11-07)
- ✅ **Funcionó:** escribir primero una especificación (`SPEC.md`) y construir contra ella.
- ✅ **Funcionó:** reutilizar la hoja y las variables del bot (`${{worker.*}}` en Railway) en lugar de crear otra base.
- ⚠️ **Mejorar:** se trabajó en copias de carpeta (`vuelto-foto`, `vuelto-web`) antes de usar git; las ramas resuelven eso (DT-3).
- ⚠️ **Mejorar:** el prompt de lectura y las categorías se copiaron del bot a la web (DT-4).
