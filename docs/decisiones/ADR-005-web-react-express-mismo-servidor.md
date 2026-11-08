# ADR-005: Web con React + Express en un solo servicio y login por contraseña

- **Fecha:** 2026-11-07 · **Estado:** Aceptada (retroactivo) · **Sprint:** 3

## Contexto
La web necesitaba leer y escribir en Google Sheets sin exponer la credencial de la cuenta de servicio en el navegador,
y ser privada para un único usuario.

## Decisión
Un solo servicio Node: Express sirve la app React compilada (Vite) y una API `/api/*` que habla con Google Sheets.
Acceso con contraseña, sesión firmada de larga duración y bloqueo temporal ante intentos fallidos repetidos.
Imagen Docker multi-etapa: la imagen final solo lleva el servidor y la app compilada.

## Alternativas consideradas
- **Frontend estático que llama directo a Google** — descartada: expondría credenciales.
- **Proveedor de identidad (Auth0, Google Sign-In)** — descartada por ahora: complejidad innecesaria para un usuario.

## Consecuencias
- ✅ Un despliegue, un dominio; credencial solo en el servidor.
- ⚠️ La autenticación es de un solo usuario; para varios usuarios habría que migrar a un proveedor de identidad.
