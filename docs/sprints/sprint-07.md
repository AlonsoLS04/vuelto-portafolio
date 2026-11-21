# Sprint 7 — Información de IA en las tarjetas

> Versión pública y resumida. El detalle operativo del sprint se gestiona en el repositorio privado.

- **Fechas:** 2026-11-15 → 2026-11-20
- **Objetivo:** quitar de la vista del usuario la información técnica de IA sin perder esos datos.
- **Versión:** v1.2.0
- **Resultado:** ✅ Objetivo cumplido · 4 de 4 puntos de producto (más una tarea de operación de 1 punto; un bug de 2 puntos descartado por el PO)

## Regla del sprint
Vuelto está en producción. Ningún cambio de configuración se hace sin un plan de vuelta atrás. Todo cambio pasa por
rama + Pull Request y se verifica el despliegue después de cada merge. Cada historia entra con tests y el CI en verde.
Antes de empezar una historia se leen también los comentarios de su issue (acción de la retrospectiva del Sprint 6).

## Historias completadas
| ID | Historia | Puntos | Incremento |
|----|----------|--------|------------|
| HU-IA.3 | Guardar los datos de IA aunque no se muestren | 2 | La web y el bot guardan el método de registro y la fuente de la categoría en dos columnas nuevas de la hoja; las filas antiguas y los reportes de Power BI no cambian |
| HU-IA.1 | Quitar "IA xx%" de la tarjeta de vista previa | 1 | La vista previa muestra solo categoría y fecha; con foto se mantiene "Leído de la foto" |
| HU-IA.2 | Quitar la línea "IA: …" del detalle del movimiento | 1 | El detalle se ve igual en un movimiento manual y en uno leído por IA, sin recuadros vacíos |

- **Cambio de alcance:** HU-IA.3 iba a guardar también la confianza de la IA. Se quitó porque el modelo no la devuelve y el valor que se mostraba era fijo: no se guardan datos inventados (de 3 a 2 puntos).
- **Descartado:** BUG-1 (coherencia entre tipo, categoría y color del monto, 2 pts). Decisión del PO: el cambio manual entre Gasto e Ingreso ya existe en la web y en Telegram.
- **Tests:** la web pasó de 109 a 128 tests (Vitest) y el bot de 124 a 137 (pytest).

## Registro diario
| Fecha | Hecho | Siguiente |
|-------|-------|-----------|
| 2026-11-15 | Sprint 6 cerrado; Sprint 7 por planificar | Sprint Planning |
| 2026-11-20 | Tarea de operación de la infraestructura completada. El PO descarta BUG-1 y quita la confianza de HU-IA.3 | HU-IA.3 |
| 2026-11-20 | HU-IA.3, HU-IA.1 y HU-IA.2 completadas, cada una desplegada y verificada en el teléfono. Sprint Review y Retrospectiva | Sprint 8 |

## Sprint Review (2026-11-20)
El PO aceptó las 4 historias del sprint. Todas cumplen la Definición de Hecho y están desplegadas y verificadas.
Los datos de IA se verificaron en producción: un movimiento nuevo desde la web y otro desde el bot llenan las columnas
nuevas, las filas antiguas quedan vacías y Power BI sigue actualizando sin errores.

## Retrospectiva (2026-11-20)
- ✅ **Funcionó:** se cumplió la acción del Sprint 6: se leyeron los comentarios de cada issue antes de empezar y ninguna objeción del PO quedó fuera del backlog.
- ✅ **Funcionó:** cada historia pasó por Pull Request con CI en verde, despliegue verificado y prueba del PO; ningún cambio interrumpió el servicio.
- ⚠️ **Mejorar:** el alcance cambió varias veces durante el sprint y el objetivo y las fechas no se cerraron en la planificación.
- ⚠️ **No funcionó:** un mensaje de commit con comillas se rompió en la terminal de Windows y el commit no se creó a la primera.
- 🔁 **Acción para el Sprint 8:** los mensajes de commit y de Pull Request se escriben primero en un archivo y se pasan desde ahí.
