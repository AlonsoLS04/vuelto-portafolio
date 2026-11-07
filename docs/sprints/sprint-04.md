# Sprint 4 — Ingresos en la web

- **Fecha:** 2026-11-07
- **Objetivo:** que la web muestre, registre y edite ingresos con las mismas categorías del bot, sin afectar el presupuesto.
- **Versión:** v0.4.0 (commit `bc0de4e` — "ingresos en la web")
- **Resultado:** ✅ Objetivo cumplido

## Historias completadas
HU-6.8 · HU-7.5

## Incremento entregado
- El servidor lee filas de tipo `ingreso` además de `gasto` y deja de bloquear su edición y borrado.
- La lectura de vouchers en la web reconoce ingresos ("Te yapearon", "Abono por traspaso", "Transferencia recibida") con categorías `sueldo`, `freelance`, `otros`.
- Presupuestos y topes siguen contando solo gastos.

## Evidencia
Commit `bc0de4e` (12:58); cambios en `server.js`, `store.jsx`, `budget.js`, `categories.jsx`, `QuickAdd.jsx`, `TransactionEditor.jsx`, `Dashboard.jsx`.

## Retrospectiva (lecciones aprendidas, escritas el 2026-11-07)
- ✅ **Funcionó:** sprint pequeño con un objetivo único y verificable.
- ✅ **Funcionó:** mantener la regla de negocio explícita ("el presupuesto solo cuenta gastos").
- ⚠️ **Mejorar:** el mensaje de commit no referenciaba la historia; desde el Sprint 5 se usa `[HU-x.y]`.
