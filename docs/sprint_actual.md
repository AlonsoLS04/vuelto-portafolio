# Sprint 5: Profesionalización

- **Objetivo del sprint:** dejar Vuelto listo para mostrarse como proyecto de portafolio —seguro, versionado, probado y documentado— **sin interrumpir el servicio en uso**.
- **Fechas:** 2026-11-08 → 2026-11-21 · **Versión objetivo:** v1.0.0
- **Capacidad:** 12 puntos

## Regla del sprint
Vuelto está en producción. Ninguna tarea cambia variables de entorno, nombres de pestañas de la hoja o el comando
de arranque sin un plan de vuelta atrás. Los cambios se hacen en ramas y se verifican en Railway después de cada merge.

## Historias comprometidas
| ID | Historia | Puntos | Estado |
|----|----------|--------|--------|
| HU-9.1 | Documentación Scrum retroactiva | 2 | ✅ Hecha |
| HU-9.3 | Corregir hallazgos de la auditoría | 2 | ✅ Hecha |
| HU-9.2 | Carpeta del bot enlazada a su repo privado | 1 | ✅ Hecha |
| HU-9.4 | Tests + CI | 5 | ⏳ Pendiente |
| HU-9.5 | Repositorio público de caso de estudio | 2 | 🔄 En curso |

## Tareas
| ID | Tarea | HU | Estado | Notas |
|----|-------|----|--------|-------|
| T1 | Crear `docs/` con backlog, sprints 1–4, ADR, arquitectura y DoD | HU-9.1 | ✅ | Reconstruido desde código, commits y fechas |
| T2 | Configurar `git config user.email` con el correo `noreply` de GitHub | DT-9 | ✅ | Correo `noreply` ya configurado globalmente. El PO pidió corregir también el historial: 3 commits del 2026-11-07 en `Vuelto-web.io` reescritos (force push con respaldo), tags v0.3.0/v0.4.0 movidos, código idéntico y despliegue verificado |
| T3 | Renombrar `dockerignore` → `.dockerignore` en el bot | HU-9.3 | ✅ | Variables de Railway verificadas antes; commit en `MyFinanzas.io` y despliegue exitoso el 2026-11-07 |
| T4 | Retirar la sección fuera de alcance de `SPEC.md` | HU-9.3 | ✅ | Solo documentación |
| T5 | Enlazar la carpeta local del bot con `MyFinanzas.io` (`git init` + `fetch` + `reset`) | HU-9.2 | ✅ | Carpeta local clonada desde `MyFinanzas.io`; `.env` y `credenciales.json` siguen ignorados |
| T6 | Versionar `instalar_servidor.sh` en el repo del bot | HU-9.2 | ✅ | PR #4 en `MyFinanzas.io`; despliegue en Railway exitoso el 2026-11-08 |
| T7 | Crear repositorio **público** `vuelto-portafolio` (caso de estudio sin código) y subir la documentación | HU-9.5 | 🔄 | Repo creado; falta el primer push |
| T8 | Tests de `nlpParser`, `budget`, `recurring` (Vitest) y de `parse_amount` / `parse_date` (pytest) | HU-9.4 | ⏳ | `SPEC.md` §5.4 ya trae casos de prueba |
| T9 | GitHub Actions: build + tests en cada push | HU-9.4 | ⏳ | |
| T10 | Capturas con datos ficticios (hoja de demo aparte) | HU-9.5 | ⏳ | Nunca capturas de la hoja real |
| T11 | `/cerrar-sprint` → tag `v1.0.0` y GitHub Release | — | ⏳ | |

Estados: ⏳ Pendiente · 🔄 En curso · ✅ Hecha · ⛔ Bloqueada

## Descubierto durante el sprint
- 2026-11-08: al cerrar DT-9 se detectó que los commits locales no están firmados (sin *Verified*). Se agregó al backlog como DT-10 (AlonsoLS04/Vuelto-web.io#16) para un sprint futuro; no cambia el alcance del Sprint 5.

## Registro diario
| Fecha | Hecho | Siguiente | Bloqueos |
|-------|-------|-----------|----------|
| 2026-11-07 | Auditoría y documentación retroactiva (T1). PO decide: código privado + repo público de caso de estudio. Hallazgo corregido: el bot sí estaba en GitHub (`MyFinanzas.io`). T3 y T4 hechas | T2, T5, T7 | — |
| 2026-11-08 | Tablero en GitHub (Project Vuelto, milestone Sprint 5, 14 issues). PO completa HU-9.2 (T5, T6): PR #4 en `MyFinanzas.io`, issue cerrado y despliegue del bot verificado. T2 (DT-9): historial de `Vuelto-web.io` corregido con force push; respaldo en `_respaldo/` | T7 | — |

## Riesgo detectado
- Railway está en plan **Trial** (crédito limitado). Al agotarse, los servicios se detienen. Decisión del PO pendiente: elegir plan o alternativa.
