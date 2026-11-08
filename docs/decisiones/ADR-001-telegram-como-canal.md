# ADR-001: Telegram como canal de captura

- **Fecha:** 2026-10-24 · **Estado:** Aceptada (retroactivo) · **Sprint:** 1

## Contexto
Registrar un gasto debe tomar segundos y desde el celular. La primera idea era una app propia tipo MonAi en React,
pero eso exigía construir cámara, autenticación e instalación antes de validar el valor principal: leer el voucher.

## Decisión
Usar un bot de Telegram como primera interfaz: el usuario envía la foto y confirma con botones.

## Alternativas consideradas
- **WhatsApp** — descartada: la API oficial exige cuenta de negocio, plantillas y costo por conversación.
- **App propia desde el inicio** — pospuesta: mucho trabajo antes de validar la lectura de vouchers (llegó en el Sprint 3 como web).

## Consecuencias
- ✅ Cámara, notificaciones e historial "gratis"; MVP en un día.
- ✅ Bot privado: solo responde a usuarios autorizados.
- ⚠️ La experiencia visual queda limitada a mensajes y botones; se complementa con la web.
