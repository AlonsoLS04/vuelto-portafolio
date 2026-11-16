# ADR-003: Lectura de comprobantes con Gemini y alternativa Claude

- **Fecha:** 2026-10-24 · **Estado:** Aceptada (retroactivo) · **Sprint:** 1

## Contexto
Los comprobantes peruanos son muy variados (POS Niubiz/Izipay, boletas, capturas de Yape/Plin, transferencias).
Un OCR clásico + reglas exigiría una plantilla por formato.

## Decisión
Enviar la imagen a un modelo de visión con un prompt que devuelve JSON (`monto`, `moneda`, `comercio`, `fecha`, `hora`,
`categoria`, `medio_pago`, `tipo`) y normalizar la respuesta en código. El proveedor es configurable:
Gemini por defecto (cuota gratuita, con modelos de respaldo en cascada) y Claude como alternativa de pago por uso.

## Alternativas consideradas
- **OCR (Tesseract) + regex** — descartada: frágil ante formatos nuevos y fotos torcidas.

## Consecuencias
- ✅ Funciona con formatos nunca vistos; categoría inferida en el mismo paso.
- ✅ El usuario siempre confirma antes de guardar, así que un error de lectura no contamina la hoja.
- ⚠️ Dependencia de un servicio externo; si falla, el bot avisa y se puede registrar por texto.
- ⚠️ El prompt existe en el bot y en la web.

## Actualización (2026-11-15, Sprint 6)
**Decisión del PO:** Vuelto usa **solo Gemini** como proveedor de IA en producción. Claude no se usa como respaldo
automático: cobra por uso y no compensa. La resiliencia se resuelve dentro de Gemini, con reintentos de espera creciente
y un segundo modelo de respaldo (HU-13.1).
