# Changelog

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/) y versionado [SemVer](https://semver.org/lang/es/).
Cada sprint cerrado genera una versión. Las versiones 0.1.0–0.4.0 se registraron de forma retroactiva.

## [Sin publicar] — Sprint 5: Profesionalización
### Añadido
- [HU-9.1] Documentación Scrum: backlog, historial de sprints, ADR, arquitectura y Definición de Hecho.
- [HU-9.5] README orientado a portafolio y repositorio público de caso de estudio.
### Corregido
- [HU-9.3] Bot: `dockerignore` renombrado a `.dockerignore`.
- [HU-9.3] `SPEC.md`: retirada una sección fuera del alcance del producto.

## [0.4.0] - 2026-11-07 — Sprint 4: Ingresos en la web
### Añadido
- [HU-6.8] La web muestra, registra y edita ingresos (sueldo, freelance, otros).
- La lectura de vouchers en la web reconoce ingresos ("Te yapearon", "Abono por traspaso").
### Cambiado
- [HU-7.5] Presupuestos y topes siguen contando solo gastos.

## [0.3.0] - 2026-11-07 — Sprint 3: App web conectada a la misma hoja
### Añadido
- [HU-6.1–6.7] App web: inicio con barras por categoría, movimientos, registro por foto/texto/voz, edición y división, rediseño e ícono para iPhone.
- [HU-7.1–7.4] Presupuestos, alertas por categoría, recurrentes y configuración sincronizada en `WebConfig`.
- [HU-8.2–8.3] Login con contraseña, sesión firmada de 60 días y bloqueo tras 5 intentos.
- [HU-4.3, HU-5.4] Web desplegada en Railway sobre la misma hoja del bot.

## [0.2.0] - 2026-10-25 — Sprint 2: Vuelto 24/7
### Añadido
- [HU-5.1–5.3] Dockerfile, Procfile y script de instalación como servicio; bot desplegado en Railway.

## [0.1.0] - 2026-10-24 — Sprint 1: MVP del bot
### Añadido
- [HU-1.1–1.5] Lectura de comprobantes por foto con Gemini o Claude y confirmación con botones.
- [HU-2.1–2.4] Registro y corrección por texto.
- [HU-3.1–3.4] Comandos `/resumen`, `/ultimos`, `/deshacer`, `/hoja`.
- [HU-4.1–4.2] Registro en Google Sheets con tipos listos para Power BI.
- [HU-8.1] Bot privado por lista de IDs.
