# Sprint 6 — Lectura de vouchers resiliente

> Versión pública y resumida. El detalle operativo del sprint se gestiona en el repositorio privado.

- **Fechas:** 2026-11-12 → 2026-11-15 (cerrado antes de la fecha prevista, el 2026-12-05)
- **Objetivo:** que leer un voucher nunca muestre errores técnicos al usuario, ni en la web ni en el bot, aunque el servicio de IA esté saturado.
- **Versión:** v1.1.0
- **Resultado:** ✅ Objetivo cumplido · 9 de 9 puntos de producto (una historia de 3 puntos descartada por el PO)

## Regla del sprint
Vuelto está en producción. Ningún cambio de configuración se hace sin un plan de vuelta atrás. Todo cambio pasa por
rama + Pull Request y se verifica el despliegue después de cada merge. Cada historia entra con tests y el CI en verde
(acción de la retrospectiva del Sprint 5).

## Historias completadas
| ID | Historia | Puntos | Incremento |
|----|----------|--------|------------|
| HU-13.1 | Reintento automático si la IA está saturada (web y bot) | 2 | Reintentos con espera creciente y un modelo de respaldo del mismo proveedor; tope de tiempo para no dejar al usuario esperando |
| HU-13.2 | Web: mensaje claro y botón "Reintentar" | 2 | Sin códigos técnicos en pantalla; "Reintentar" reenvía la misma foto sin volver a adjuntarla |
| HU-13.3 | Bot: aviso de "leyendo" y botón "Reintentar" | 2 | El mensaje "Leyendo tu voucher…" se reemplaza por el resultado; si falla, un botón relee la misma foto |
| HU-13.5 | Comprimir la imagen antes de enviarla a la IA | 1 | El bot comprime las imágenes enviadas como archivo |
| HU-13.4 | Registrar cada fallo de la IA | 2 | Cada lectura con reintentos o fallida queda registrada (canal, código, intentos, duración), con el mismo formato en web y bot |

- **Descartada:** HU-13.6 (proveedor de IA de respaldo de otra empresa, 3 pts). Decisión del PO: Vuelto usa un solo proveedor (Gemini); un segundo proveedor de pago no compensa, y el modelo de respaldo de HU-13.1 ya cubre el caso.
- **Trabajo adicional (deuda técnica):** el CI de la web construye y arranca la imagen Docker; publicación automatizada y revisada de este caso de estudio.
- **Tests:** la web pasó de 53 a 109 tests (Vitest) y el bot de 53 a 124 (pytest).

## Registro diario
| Fecha | Hecho | Siguiente |
|-------|-------|-----------|
| 2026-11-14 | Publicación automatizada y revisada del caso de estudio | HU-13.1 |
| 2026-11-15 | HU-13.1, 13.2, 13.3, 13.5 y 13.4 completadas, cada una desplegada y probada con una foto real. El PO descarta HU-13.6. Sprint Review y Retrospectiva | Sprint 7 |

## Sprint Review (2026-11-15)
El PO aceptó las 5 historias de producto y la deuda técnica del sprint. Todas cumplen la Definición de Hecho y están desplegadas y verificadas.
Cada cambio se probó primero con una simulación del servicio de IA saturado y, tras el despliegue, con una foto real en el teléfono.

## Retrospectiva (2026-11-15)
- ✅ **Funcionó:** todo lo comprometido que seguía vigente se entregó, sin interrumpir el servicio.
- ✅ **Funcionó:** se cumplió la acción del Sprint 5: los cambios de alcance se registraron antes de empezarlos y cada historia entró con tests y CI en verde.
- ⚠️ **No funcionó:** una historia se planificó con un proveedor de IA de pago que no compensa; se descartó al final del sprint.
- ⚠️ **Mejorar:** el PO ya había objetado esa historia en un comentario del issue, pero la objeción no pasó al backlog.
- 🔁 **Acción para el Sprint 7:** antes de planificar o empezar una historia, leer también los comentarios de su issue y llevar cualquier objeción del PO al backlog.
