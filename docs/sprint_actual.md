# Sprint 5: Profesionalización

> Versión pública y resumida. El detalle operativo del sprint se gestiona en el repositorio privado.

- **Objetivo del sprint:** dejar Vuelto listo para mostrarse como proyecto de portafolio —seguro, versionado, probado y documentado— **sin interrumpir el servicio en uso**.
- **Fechas:** 2026-11-08 → 2026-11-21 · **Versión objetivo:** v1.0.0
- **Capacidad:** 12 puntos

## Regla del sprint
Vuelto está en producción. Ningún cambio de configuración se hace sin un plan de vuelta atrás. Todo cambio pasa por
rama + Pull Request y se verifica el despliegue después de cada merge.

## Historias comprometidas
| ID | Historia | Puntos | Estado |
|----|----------|--------|--------|
| HU-9.1 | Documentación Scrum retroactiva | 2 | ✅ Hecha |
| HU-9.3 | Corregir hallazgos de la auditoría | 2 | ✅ Hecha |
| HU-9.2 | Código del bot gestionado con git (commits y ramas) | 1 | ✅ Hecha |
| HU-9.4 | Tests + CI | 5 | ⏳ Pendiente |
| HU-9.5 | Repositorio público de caso de estudio | 2 | ✅ Hecha |

## Tareas
| ID | Tarea | HU | Estado |
|----|-------|----|--------|
| T1 | Backlog, historial de sprints, ADR, arquitectura y Definición de Hecho | HU-9.1 | ✅ |
| T2 | Autoría de commits vinculada al perfil de GitHub | Deuda técnica | ✅ |
| T3 | Corregir la exclusión de archivos locales en la imagen Docker del bot | HU-9.3 | ✅ |
| T4 | Retirar de la especificación una sección fuera de alcance | HU-9.3 | ✅ |
| T5 | Enlazar la carpeta local del bot con su repositorio | HU-9.2 | ✅ |
| T6 | Versionar el script de instalación alternativo del bot | HU-9.2 | ✅ |
| T7 | Publicar este repositorio de caso de estudio | HU-9.5 | ✅ |
| T8 | Tests de parsers, presupuesto y recurrentes (Vitest y pytest) | HU-9.4 | ⏳ |
| T9 | GitHub Actions: build + tests en cada push | HU-9.4 | ⏳ |
| T10 | Capturas con datos ficticios | HU-9.5 | ✅ |
| T11 | Cierre del sprint: versión `v1.0.0` y GitHub Release | — | ⏳ |
| T12 | Versión curada para el público: sin detalle de seguridad, infraestructura ni guías operativas | HU-9.5 | ✅ |

Estados: ⏳ Pendiente · 🔄 En curso · ✅ Hecha · ⛔ Bloqueada

## Registro diario
| Fecha | Hecho | Siguiente |
|-------|-------|-----------|
| 2026-11-07 | Auditoría y documentación retroactiva. El PO decide: código privado + repositorio público de caso de estudio. T3 y T4 hechas | T2, T5, T7 |
| 2026-11-08 | Tablero en GitHub Projects con milestone del sprint. HU-9.2 completada (T5, T6). T2 completada. HU-9.5 completada: versión curada (T12), publicación (T7) y capturas con datos ficticios (T10) | HU-9.4 |
