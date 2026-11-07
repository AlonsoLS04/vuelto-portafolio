# ADR-005: Web con React + Express en un solo servicio y login por contraseña

- **Fecha:** 2026-11-07 · **Estado:** Aceptada (retroactivo) · **Sprint:** 3

## Contexto
La web necesitaba leer y escribir en Google Sheets sin exponer la credencial de la cuenta de servicio en el navegador,
y ser privada para un único usuario.

## Decisión
Un solo servicio Node: Express sirve la app React compilada (Vite) y una API `/api/*` que habla con Google Sheets.
Acceso con una contraseña (`APP_PASSWORD`), cookie de sesión firmada con HMAC por 60 días y bloqueo de 5 minutos
tras 5 intentos fallidos por IP. Imagen Docker multi-etapa: la imagen final solo lleva `server.js` y `dist/`.

## Alternativas consideradas
- **Frontend estático que llama directo a Google** — descartada: expondría credenciales.
- **Proveedor de identidad (Auth0, Google Sign-In)** — descartada por ahora: complejidad innecesaria para un usuario.

## Consecuencias
- ✅ Un despliegue, un dominio; credencial solo en el servidor.
- ⚠️ El control de intentos vive en memoria y se reinicia con cada despliegue. Aceptable para uso personal.
