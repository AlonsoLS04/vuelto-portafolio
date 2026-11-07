# Definición de Hecho (DoD) — Vuelto

Una historia está **Hecha** cuando cumple todo esto:

- [ ] Cumple todos sus criterios de aceptación.
- [ ] El PO la probó en local (`npm run build && npm start` o `python bot.py`).
- [ ] El flujo principal sigue funcionando: foto → borrador → guardar → aparece en la hoja y en la web.
- [ ] No hay secretos ni datos personales reales en el código, en el commit ni en la imagen Docker.
- [ ] No cambia nombres de variables de entorno, pestañas (`Movimientos`, `WebConfig`) ni columnas de la hoja; si lo hace, hay ADR y plan de migración.
- [ ] Errores esperables muestran un mensaje claro al usuario.
- [ ] Documentación actualizada (`docs/arquitectura.md`, README, `.env.example`).
- [ ] Commit con Conventional Commits y referencia `[HU-x.y]`.
- [ ] Tests nuevos o actualizados y CI en verde (desde HU-9.4).
- [ ] Desplegado en Railway y verificado en el iPhone.
