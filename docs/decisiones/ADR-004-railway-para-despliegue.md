# ADR-004: Railway para el despliegue

- **Fecha:** 2026-10-25 · **Estado:** Aceptada (retroactivo) · **Sprint:** 2

## Contexto
El bot debía responder 24/7 sin depender de la laptop.

## Decisión
Empaquetar el bot en Docker y desplegarlo en Railway como servicio `worker`, conectado al repositorio privado de GitHub con despliegue automático al hacer push a `main`, usando *polling*.
En el Sprint 3 la web se agregó como segundo servicio del mismo proyecto, reutilizando variables con `${{worker.*}}`.

## Alternativas consideradas
- **VM gratuita (Google Cloud / Oracle) con `systemd`** — preparada (`instalar_servidor.sh`) pero no elegida: más mantenimiento (actualizaciones, reinicios, seguridad del servidor).
- **Webhooks** — descartados: requieren dominio y HTTPS; *polling* basta para un usuario.

## Consecuencias
- ✅ Despliegue desde la interfaz, logs en el panel y variables compartidas entre servicios.
- ⚠️ El disco es efímero: los borradores del bot (`PicklePersistence`) se pierden en cada redeploy (DT-5). Aceptado: un borrador perdido solo obliga a reenviar la foto.
- ⚠️ Plan Trial con crédito limitado: al agotarse, los servicios se detienen.
- ⚠️ Durante cada despliegue el contenedor nuevo y el viejo se solapan unos segundos; Telegram responde `Conflict: terminated by other getUpdates request` una vez y el bot se recupera solo.
