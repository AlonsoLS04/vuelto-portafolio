# Sprint 2 — Vuelto disponible 24/7

- **Fecha:** 2026-10-25
- **Objetivo:** que el bot responda aunque la laptop esté apagada.
- **Versión:** v0.2.0
- **Resultado:** ✅ Objetivo cumplido (bot corriendo 24/7 en Railway)

## Historias completadas
HU-5.1 · HU-5.2 · HU-5.3

## Incremento entregado
| Componente | Qué hace |
|-----------|----------|
| `Dockerfile` | Imagen ligera de Python con logs visibles en el panel del servidor |
| `Procfile` | Define el proceso del bot |
| Script de instalación | Instala el bot como servicio en una VM Linux (alternativa evaluada) |
| Credenciales por variable de entorno | Ningún archivo de credenciales se sube al servidor |

## Evidencia
Archivos de contenedor del 2026-10-25, primeros commits en el repositorio privado del bot conectado a despliegue automático y script de instalación en VM como alternativa.

## Decisiones técnicas
- [ADR-004](../decisiones/ADR-004-railway-para-despliegue.md) Railway para el despliegue (frente a una VM gratuita)

## Retrospectiva (lecciones aprendidas, escritas el 2026-11-07)
- ✅ **Funcionó:** usar *polling* en lugar de webhooks: no hizo falta dominio ni certificados.
- ✅ **Funcionó:** preparar dos caminos de despliegue (Railway y VM) y elegir el más simple.
- ⚠️ **Mejorar:** faltó un checklist de seguridad en la Definición de Hecho para revisar qué archivos entran en la imagen; se agregó en el Sprint 5.
