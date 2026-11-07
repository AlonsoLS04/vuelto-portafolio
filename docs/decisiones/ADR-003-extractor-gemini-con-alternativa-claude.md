# ADR-003: Lectura de comprobantes con Gemini y alternativa Claude

- **Fecha:** 2026-10-24 · **Estado:** Aceptada (retroactivo) · **Sprint:** 1

## Contexto
Los comprobantes peruanos son muy variados (POS Niubiz/Izipay, boletas, capturas de Yape/Plin, transferencias).
Un OCR clásico + reglas exigiría una plantilla por formato.

## Decisión
Enviar la imagen a un modelo de visión con un prompt que devuelve JSON (`monto`, `moneda`, `comercio`, `fecha`, `hora`,
`categoria`, `medio_pago`, `tipo`) y normalizar la respuesta en código. Proveedor configurable con `EXTRACTOR`:
Gemini por defecto (cuota gratuita, modelos en cascada vía `GEMINI_MODEL`) y Claude como alternativa de pago por uso.

## Alternativas consideradas
- **OCR (Tesseract) + regex** — descartada: frágil ante formatos nuevos y fotos torcidas.

## Consecuencias
- ✅ Funciona con formatos nunca vistos; categoría inferida en el mismo paso.
- ✅ El usuario siempre confirma antes de guardar, así que un error de lectura no contamina la hoja.
- ⚠️ Dependencia de un servicio externo; si falla, el bot avisa y se puede registrar por texto.
- ⚠️ El prompt existe en el bot y en la web (DT-4).
