# ADR-002: Google Sheets como fuente única de datos

- **Fecha:** 2026-10-24 · **Estado:** Aceptada (retroactivo) · **Sprint:** 1 (reafirmada en el 3)

## Contexto
El objetivo final es analizar los gastos en Power BI. Se necesitaba un almacenamiento gratuito, editable a mano,
consultable desde el celular y con conector nativo a Power BI.

## Decisión
Guardar cada movimiento como una fila en la pestaña `Movimientos` de una hoja de Google, con fecha y monto tipados.
En el Sprint 3 la web usa la misma hoja y guarda su configuración en la pestaña `WebConfig`.

## Alternativas consideradas
- **Base de datos (PostgreSQL / SQLite)** — pospuesta: costo y mantenimiento sin necesidad aún (HU-11.2).
- **Excel local** — descartada: no accesible desde el servidor ni el celular.

## Consecuencias
- ✅ Cero costo, edición manual posible y conector directo a Power BI.
- ✅ Bot y web sincronizados sin construir una API común.
- ⚠️ Sin transacciones ni índices; límites de cuota de la API de Sheets. Aceptable para un solo usuario.
