# Sprint 6: Lectura de vouchers resiliente

> Versión pública y resumida. El detalle operativo del sprint se gestiona en el repositorio privado.

- **Objetivo del sprint:** que leer un voucher nunca muestre errores técnicos al usuario, ni en la web ni en el bot, aunque el servicio de IA esté saturado.
- **Fechas:** 2026-11-12 → 2026-12-05 · **Versión objetivo:** v1.1.0
- **Capacidad:** 12 puntos

## Regla del sprint
Vuelto está en producción. Ningún cambio de configuración se hace sin un plan de vuelta atrás. Todo cambio pasa por
rama + Pull Request y se verifica el despliegue después de cada merge. Cada historia entra con tests y el CI en verde
(acción de la retrospectiva del Sprint 5).

## Historias comprometidas
| ID | Historia | Puntos | Estado |
|----|----------|--------|--------|
| HU-13.1 | Reintento automático si la IA está saturada (web y bot) | 2 | ⏳ Pendiente |
| HU-13.2 | Web: mensaje claro y botón "Reintentar" si la lectura falla | 2 | ⏳ Pendiente |
| HU-13.3 | Bot: aviso de "leyendo" y mensaje claro con botón "Reintentar" si falla | 2 | ⏳ Pendiente |
| HU-13.5 | Comprimir la imagen antes de enviarla a la IA | 1 | ⏳ Pendiente |
| HU-13.4 | Registrar cada fallo de la IA para medir su frecuencia | 2 | ⏳ Pendiente |
| HU-13.6 | Proveedor de IA de respaldo si el principal sigue saturado | 3 | ⏳ Pendiente |

Estados: ⏳ Pendiente · 🔄 En curso · ✅ Hecha · ⛔ Bloqueada

## Registro diario
| Fecha | Hecho | Siguiente |
|-------|-------|-----------|
