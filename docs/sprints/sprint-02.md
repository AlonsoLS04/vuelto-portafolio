# Sprint 2 — Vuelto disponible 24/7

- **Fecha:** 2026-10-25
- **Objetivo:** que el bot responda aunque la laptop esté apagada.
- **Versión:** v0.2.0
- **Resultado:** ✅ Objetivo cumplido (bot corriendo como servicio `worker` en Railway)

## Historias completadas
HU-5.1 · HU-5.2 · HU-5.3

## Incremento entregado
| Componente | Qué hace |
|-----------|----------|
| `Dockerfile` | Imagen `python:3.12-slim` con logs sin buffer para el panel del servidor |
| `Procfile` | Define el proceso `worker: python bot.py` |
| `instalar_servidor.sh` | Instala el bot como servicio `systemd` en una VM Debian/Ubuntu (alternativa evaluada) |
| Credenciales por variable | `GOOGLE_CREDENTIALS_JSON` para no subir el archivo JSON al servidor |

## Evidencia
`Dockerfile` y `dockerignore` (11:29) del 2026-10-25; código subido al repositorio privado `MyFinanzas.io` (commits de las 11:41 y 11:43) y conectado a Railway con despliegue automático; `instalar_servidor.sh` (11:59) como alternativa.

## Decisiones técnicas
- [ADR-004](../decisiones/ADR-004-railway-para-despliegue.md) Railway para el despliegue (frente a una VM gratuita)

## Retrospectiva (lecciones aprendidas, escritas el 2026-11-07)
- ✅ **Funcionó:** usar *polling* en lugar de webhooks: no hizo falta dominio ni certificados.
- ✅ **Funcionó:** preparar dos caminos de despliegue (Railway y VM) y elegir el más simple.
- ⚠️ **Mejorar:** el archivo `dockerignore` quedó sin el punto inicial y Docker no lo aplica (DT-1). Un checklist de seguridad en la Definición de Hecho lo habría detectado.
