# ADR-006: Web "agregar a inicio" en lugar de app nativa

- **Fecha:** 2026-11-07 · **Estado:** Aceptada (retroactivo) · **Sprint:** 3

## Contexto
La visión incluye tener Vuelto como app en el iPhone, pero publicar en App Store exige cuenta de desarrollador, revisión y otro stack.

## Decisión
Diseñar la web para pantalla de teléfono, con `apple-touch-icon`, para agregarla a la pantalla de inicio desde Safari.

## Alternativas consideradas
- **App nativa / React Native** — pospuesta (HU-12.3, Won't por ahora).

## Consecuencias
- ✅ Experiencia de app sin tiendas ni costos.
- ⚠️ Sin acceso a notificaciones de otras apps (por eso la captura automática de Yape requiere un spike, SP-1).
