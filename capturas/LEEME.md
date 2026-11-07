# Capturas

Aquí van las imágenes que usa el README. **Nunca captures tu hoja ni tus movimientos reales.**

Cómo obtener capturas con datos ficticios sin tocar producción:
1. Crea una hoja de Google nueva ("Vuelto DEMO") y compártela como Editor con la misma cuenta de servicio.
2. En tu PC, dentro de `vuelto-web`, crea un `.env` con `SHEET_ID` = el ID de la hoja DEMO y una `APP_PASSWORD` cualquiera.
3. `npm run build` y `npm start`, abre `http://localhost:3000` y registra 15–20 gastos inventados (Tambo, Metropolitano, Netflix…).
4. Captura en modo teléfono (F12 → icono de móvil en Chrome/Edge) y guarda aquí: `web-inicio.png`, `web-presupuesto.png`, `web-foto.png`.
5. Para el bot, captura una conversación con un voucher de ejemplo (no uno tuyo) → `bot-voucher.png`.
6. Descomenta la línea de imágenes en el `README.md`.
