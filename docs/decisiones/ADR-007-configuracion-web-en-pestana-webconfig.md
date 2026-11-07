# ADR-007: Configuración de la web en la pestaña `WebConfig`

- **Fecha:** 2026-11-07 · **Estado:** Aceptada (retroactivo) · **Sprint:** 3

## Contexto
El prototipo guardaba presupuestos, recurrentes y reglas aprendidas en `localStorage`, así que la laptop y el celular
mostraban cosas distintas.

## Decisión
Guardar esa configuración en una pestaña `WebConfig` de la misma hoja, leída y escrita por el servidor.

## Alternativas consideradas
- **`localStorage`** — descartada: no se sincroniza entre dispositivos.
- **Base de datos aparte** — descartada: segunda fuente de datos que mantener (ver ADR-002).

## Consecuencias
- ✅ Mismo estado en todos los dispositivos, sin infraestructura nueva.
- ⚠️ Si alguien borra la pestaña se pierde la configuración (advertido en el README).
