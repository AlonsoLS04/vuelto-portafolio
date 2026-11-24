# Sprint 8 — Identidad visual

> Versión pública y resumida. El detalle operativo del sprint se gestiona en el repositorio privado.

- **Fechas:** 2026-11-21 → 2026-11-23 (planificado el 2026-11-16)
- **Objetivo:** que Vuelto tenga una identidad visual propia y no genérica, elegida con prototipos reales y aplicada al sistema de diseño, a los montos y al Resumen.
- **Versión:** v1.3.0
- **Resultado:** ✅ Objetivo cumplido · 15 de 15 puntos comprometidos (más ~3 por un cambio de alcance aprobado por el PO)

## Regla del sprint
- Solo cambia la interfaz de la web: no se tocan el bot, la hoja de datos ni la configuración.
- **Demo antes de producción:** cada historia se integra en una rama aparte y el PO la prueba en una demo local; al final,
  con su OK, un único Pull Request lleva todo a producción.
- Cada historia entra con tests y el CI en verde. Las capturas usan solo datos ficticios.

## Historias completadas
| ID | Historia | Puntos | Incremento |
|----|----------|--------|------------|
| SP-6 | Elegir la dirección visual con prototipos | 3 | 4 direcciones prototipadas (4 pantallas cada una) y una hoja de elección. El PO eligió fondo casi negro, acento verde lima y la tipografía Space Grotesk |
| HU-UI.1 | Sistema de diseño único | 3 | Colores, radios y tamaños de texto definidos en un solo lugar; fuente alojada en la propia app; contraste WCAG AA verificado con tests |
| HU-UI.2 | Montos alineados | 2 | Un solo componente para todo el dinero: cifras de ancho igual en listas (los céntimos quedan alineados) y cifras proporcionales en el saldo grande |
| HU-UI.3 | Resumen rediseñado | 5 | "Disponible de tu presupuesto" como cifra principal, "Puedes gastar por día" y tarjetas de ingresos y balance del mes; zonas táctiles de al menos 44 px |
| HU-UI.7 | Revisión visual y auditoría de diseño | 2 | Comparación automática antes/después con Playwright y auditoría final de 22 hallazgos (19 corregidos, 1 descartado tras medirlo, 2 al backlog) |

- **Cambios de alcance aprobados por el PO:** un cuarto prototipo y 4 pantallas por prototipo en vez de solo el Resumen;
  la tipografía cambió dos veces hasta encontrar una que tuviera cifras tabulares.
- **Tests:** la web pasó de 128 a 171 tests unitarios (Vitest) y estrenó 26 pruebas visuales con Playwright y datos ficticios.
- **Peso:** el JavaScript no creció; la fuente alojada suma 22 kB.

## Registro diario
| Fecha | Hecho | Siguiente |
|-------|-------|-----------|
| 2026-11-16 | Sprint 8 planificado (15 pts) | Cerrar el Sprint 7 |
| 2026-11-21 | Rama de integración creada; capturas de la app actual como línea base; el PO aporta referencias y redefine las direcciones | Prototipos |
| 2026-11-22 | 4 prototipos aceptados; el PO elige la dirección; sistema de diseño, montos y Resumen nuevo, cada uno con demo del PO | Revisión visual final |
| 2026-11-23 | Auditoría final y demo completa; un único Pull Request lleva el sprint a producción, verificado en el teléfono | Sprint Review |

## Sprint Review (2026-11-23)
El PO aceptó las 5 historias. Todas cumplen la Definición de Hecho. Cada una se revisó en su propio Pull Request hacia la
rama de integración y el sprint completo llegó a producción en un solo paso, con demo previa y verificación en el teléfono.

El mismo día se detectó un **error de configuración del servidor**: el nombre del modelo de IA de la web estaba en el
formato que usa el bot, así que la web llevaba una semana leyendo fotos sin modelo de respaldo. Una saturación del servicio
de IA lo destapó; se corrigió sin cambiar código y se verificó con fotos reales. Tres mejoras pasaron al backlog.

## Retrospectiva (2026-11-23)
- ✅ **Funcionó:** la demo antes de producción. Cada historia se probó por separado y el rediseño completo salió sin fallos.
- ✅ **Funcionó:** pruebas que miden de verdad: el test de zonas táctiles fallaba en 6 pantallas antes del arreglo y el contraste se calcula con los colores reales.
- ✅ **Funcionó:** elegir con prototipos reales en vez de describir la idea.
- ⚠️ **No funcionó:** se comprometió más de la capacidad y el sprint no tenía fecha de fin; la auditoría final estaba subestimada.
- ⚠️ **No funcionó:** el error de configuración se veía en el registro de lecturas de IA desde hacía una semana y nadie lo revisó.
- 🔁 **Acción para el Sprint 9:** revisar el formato de la configuración de cada servicio antes de cambiarla, revisar el registro de lecturas de IA al cerrar cada sprint, y planificar con fecha de fin y compromiso dentro de la capacidad.
