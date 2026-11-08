# ADR-004: Railway para el despliegue

- **Fecha:** 2026-10-25 · **Estado:** Aceptada (retroactivo) · **Sprint:** 2

## Contexto
El bot debía responder 24/7 sin depender de la laptop.

## Decisión
Empaquetar el bot en Docker y desplegarlo en Railway con despliegue automático al hacer push a `main`, usando *polling*.
En el Sprint 3 la web se agregó como segundo servicio del mismo proyecto, compartiendo la configuración del bot.

## Alternativas consideradas
- **VM gratuita con un servicio del sistema** — preparada pero no elegida: más mantenimiento (actualizaciones, reinicios, seguridad del servidor).
- **Webhooks** — descartados: requieren dominio y HTTPS; *polling* basta para un usuario.

## Consecuencias
- ✅ Despliegue sin servidores que mantener, logs centralizados y configuración compartida entre servicios.
- ⚠️ El disco es efímero: los borradores sin confirmar del bot se pierden en cada despliegue. Aceptado: solo obliga a reenviar la foto.
- ⚠️ Durante cada despliegue el contenedor nuevo y el viejo se solapan unos segundos; el bot se recupera solo.
