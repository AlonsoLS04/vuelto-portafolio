# Product Backlog — Vuelto

**Product Owner:** Alonso
**Producto:** Vuelto (bot de Telegram + app web)
**Última actualización:** 2026-11-08

> **Nota de proceso.** Los Sprints 1 a 4 se desarrollaron en iteraciones cortas con asistencia de IA
> y se documentaron en formato Scrum de forma **retroactiva** el 2026-11-07, a partir del código, el
> historial de git y las fechas de los archivos. Desde el Sprint 5 el proyecto se gestiona con Scrum
> desde la planificación. Ver [`docs/sprints/`](sprints/).

## Visión
Para mí, que quiero saber en qué se va mi dinero sin perder tiempo anotando, **Vuelto** es un asistente de
finanzas personales que registra cada gasto o ingreso a partir de la foto del comprobante o de una frase corta.
A diferencia de las apps de presupuesto tradicionales, no exige conectar el banco ni escribir formularios,
y deja los datos en una hoja estructurada lista para analizar en Power BI.

**Fuera de alcance (por ahora):** múltiples usuarios, conexión con bancos, publicación en tiendas de apps.

## Convenciones
- ID: `HU-<épica>.<n>` · Spike: `SP-<n>` · Deuda técnica: `DT-<n>`
- Prioridad MoSCoW: **M**ust · **S**hould · **C**ould · **W**on't (por ahora)
- Puntos (solo en historias pendientes): 1, 2, 3, 5, 8
- Estado: Pendiente · En sprint N · Hecha (Sprint N)
- Seguimiento en un tablero privado de GitHub Projects. En este repositorio solo se publica el issue de HU-9.5 (#1).

---

# ✅ Completado

## Épica 1 — Captura de comprobantes por foto (bot)
> Registrar un movimiento solo enviando una foto.

| ID | Historia | Sprint |
|----|----------|--------|
| HU-1.1 | Como usuario, quiero enviar al bot la foto o captura de un voucher, boleta, Yape o Plin, para no registrar el gasto a mano. | 1 |
| HU-1.2 | Como usuario, quiero que el bot lea monto, moneda, comercio, fecha, hora, categoría y medio de pago, para que el registro sea automático. | 1 |
| HU-1.3 | Como usuario, quiero ver una tarjeta de confirmación con botones Guardar / Categoría / Descartar, para revisar antes de guardar. | 1 |
| HU-1.4 | Como usuario, quiero elegir entre Gemini (gratuito) o Claude como lector de imágenes, para controlar el costo. | 1 |
| HU-1.5 | Como usuario, quiero que una imagen que no es comprobante se rechace con un mensaje claro, para no guardar basura. | 1 |

**Criterios de aceptación de referencia (HU-1.2):**
- Dado un voucher con subtotal, IGV y total, cuando lo envío, entonces el monto registrado es el **total**.
- Dada una fecha impresa como `24/10/26`, cuando se lee, entonces se guarda como `2026-10-24`.
- Dado un voucher con número de tarjeta, cuando se lee, entonces el medio de pago **no** incluye dígitos de la tarjeta.

## Épica 2 — Registro y corrección por texto (bot)
| ID | Historia | Sprint |
|----|----------|--------|
| HU-2.1 | Como usuario, quiero registrar con texto rápido (`12.50 taxi`, `+3000 sueldo`, `us$ 10 steam`), para cuando no tengo comprobante. | 1 |
| HU-2.2 | Como usuario, quiero corregir un borrador escribiendo `monto 35.50`, `comercio Tambo`, `fecha 23/10`, `hora`, `medio` o `nota`, para arreglar errores de lectura. | 1 |
| HU-2.3 | Como usuario, quiero cambiar un borrador entre gasto e ingreso y entre soles y dólares, para registrar bien cualquier movimiento. | 1 |
| HU-2.4 | Como usuario, quiero que el texto que acompaña la foto se guarde como nota, para dar contexto al gasto. | 1 |

## Épica 3 — Consultas desde Telegram
| ID | Historia | Sprint |
|----|----------|--------|
| HU-3.1 | Como usuario, quiero `/resumen` (y `/resumen 09`) con gastos, ingresos y balance por categoría, para saber cómo voy en el mes. | 1 |
| HU-3.2 | Como usuario, quiero `/ultimos` para ver mis 5 últimos registros. | 1 |
| HU-3.3 | Como usuario, quiero `/deshacer` para borrar lo último que guardé. | 1 |
| HU-3.4 | Como usuario, quiero `/hoja` para abrir mi Google Sheets desde el chat. | 1 |

## Épica 4 — Almacenamiento y análisis
| ID | Historia | Sprint |
|----|----------|--------|
| HU-4.1 | Como usuario, quiero que cada movimiento se guarde como fila en la pestaña **Movimientos** de Google Sheets, con fecha y monto tipados, para analizarlo sin limpiar datos. | 1 |
| HU-4.2 | Como analista, quiero conectar la hoja a Power BI con medidas de Gastos, Ingresos y Balance, para construir mi dashboard. | 1 |
| HU-4.3 | Como usuario, quiero que bot y web compartan la misma hoja, para tener una sola fuente de verdad. | 3 |

## Épica 5 — Operación 24/7
| ID | Historia | Sprint |
|----|----------|--------|
| HU-5.1 | Como usuario, quiero que el bot funcione aunque mi laptop esté apagada, para registrar gastos en cualquier momento. | 2 |
| HU-5.2 | Como desarrollador, quiero el bot empaquetado en Docker con un `Procfile`, para desplegarlo en Railway. | 2 |
| HU-5.3 | Como desarrollador, quiero un script de instalación como servicio en una VM Linux, para tener una alternativa de despliegue. | 2 |
| HU-5.4 | Como usuario, quiero la app web desplegada en Railway junto al bot, compartiendo sus variables de entorno. | 3 |

## Épica 6 — App web: registro y consulta
| ID | Historia | Sprint |
|----|----------|--------|
| HU-6.1 | Como usuario, quiero un inicio con el total gastado del periodo (semana/mes/año) y barras por categoría, para ver mi situación de un vistazo. | 3 |
| HU-6.2 | Como usuario, quiero una lista de movimientos con búsqueda y filtros, para encontrar un gasto. | 3 |
| HU-6.3 | Como usuario, quiero registrar escribiendo o dictando varios gastos en una frase, para registrar en segundos. | 3 |
| HU-6.4 | Como usuario, quiero tomar o subir la foto de un voucher desde la web y confirmar antes de guardar, igual que en el bot. | 3 |
| HU-6.5 | Como usuario, quiero editar, recategorizar, dividir o borrar un movimiento, para corregir lo que la IA infirió. | 3 |
| HU-6.6 | Como usuario de iPhone, quiero agregar la web a mi pantalla de inicio con su ícono, para usarla como una app. | 3 |
| HU-6.7 | Como usuario, quiero un rediseño del inicio y una guía de estilos consistente, para que la app sea agradable de usar. | 3 |
| HU-6.8 | Como usuario, quiero ver, registrar y editar **ingresos** en la web (sueldo, freelance, otros), no solo gastos. | 4 |

## Épica 7 — Presupuestos, recurrentes y alertas (web)
| ID | Historia | Sprint |
|----|----------|--------|
| HU-7.1 | Como usuario, quiero un presupuesto mensual y topes por categoría con lo que me queda por día, para controlar mi gasto. | 3 |
| HU-7.2 | Como usuario, quiero un aviso cuando una categoría pasa el 80 % o el 100 % de su tope. | 3 |
| HU-7.3 | Como usuario, quiero registrar gastos recurrentes (suscripciones) que se publiquen solos al vencer. | 3 |
| HU-7.4 | Como usuario, quiero que presupuestos, recurrentes y reglas aprendidas se guarden en la hoja (pestaña **WebConfig**), para verlos igual en laptop y celular. | 3 |
| HU-7.5 | Como usuario, quiero que el presupuesto cuente solo gastos aunque la web muestre ingresos. | 4 |

## Épica 8 — Seguridad y privacidad
| ID | Historia | Sprint |
|----|----------|--------|
| HU-8.1 | Como usuario, quiero que solo mi ID de Telegram pueda usar el bot, para que nadie más vea o escriba mis datos. | 1 |
| HU-8.2 | Como usuario, quiero que la web pida contraseña, bloquee temporalmente los intentos fallidos repetidos y mantenga la sesión iniciada. | 3 |
| HU-8.3 | Como usuario, quiero que la credencial de Google viva solo en el servidor y nunca llegue al navegador. | 3 |

---

# 🔜 Pendiente

## Épica 9 — Profesionalización (Sprint 5)
| ID | Historia | Prioridad | Puntos | Estado |
|----|----------|-----------|--------|--------|
| HU-9.1 | Como PO, quiero el proyecto documentado con Scrum (backlog, sprints, ADR, DoD), para gestionarlo y mostrarlo en mi portafolio. | M | 2 | En sprint 5 |
| HU-9.2 | Como desarrollador, quiero la carpeta local del bot enlazada con su repositorio privado, para trabajar con commits y ramas en lugar de subir archivos por la web. | M | 1 | Hecha (Sprint 5) |
| HU-9.3 | Como PO, quiero corregir los hallazgos de la auditoría, para mantener el código limpio y seguro. | M | 2 | En sprint 5 |
| HU-9.4 | Como desarrollador, quiero tests de las funciones puras (parsers, presupuesto, recurrentes, `parse_amount`, `parse_date`) y CI en GitHub Actions. | S | 5 | En sprint 5 |
| HU-9.5 ([#1](https://github.com/AlonsoLS04/vuelto-portafolio/issues/1)) | Como PO, quiero un repositorio público de caso de estudio (sin código) con capturas de datos ficticios, para mostrar el producto manteniendo el código privado. | S | 2 | Hecha (Sprint 5) |

## Épica 10 — Captura automática de pagos
| ID | Historia | Prioridad | Puntos |
|----|----------|-----------|--------|
| SP-1 | Spike: investigar cómo capturar pagos de Yape en iPhone sin enviar nada (Atajos de iOS, correos de constancia, capturas). Entregable: recomendación con factibilidad y riesgos. | S | 3 |
| HU-10.1 | Como usuario, quiero que cada pago por Yape se registre solo y el bot me confirme por Telegram. Depende de SP-1. | C | 8 |

## Épica 11 — Datos y BI
| ID | Historia | Prioridad | Puntos |
|----|----------|-----------|--------|
| HU-11.1 | Como analista, quiero un dashboard de Power BI en modelo estrella (calendario, categorías, movimientos) publicado con capturas en el repo. | S | 5 |
| HU-11.2 | Como analista, quiero cargar la hoja a una base SQL con un proceso programado, para consultar con SQL. | C | 5 |
| HU-11.3 | Como usuario, quiero crear mis propias categorías (`/categorias`), compartidas entre bot y web. | C | 5 |

## Épica 12 — Experiencia
| ID | Historia | Prioridad | Puntos |
|----|----------|-----------|--------|
| HU-12.1 | Como usuario, quiero que la web se actualice sola cuando registro algo por Telegram, sin recargar. | C | 3 |
| HU-12.2 | Como usuario, quiero leer varias fotos de un mismo voucher largo. | C | 3 |
| HU-12.3 | Como usuario, quiero Vuelto como app nativa para iOS y Android. | W | — |

## Backlog de mejoras (lenguaje natural del PO)
<!-- Escribe aquí ideas sueltas. /planificar-sprint las convierte en historias. -->
-

## Deuda técnica
La deuda técnica se registra y prioriza en el repositorio privado. Resumen al 2026-11-08:

| Estado | Cantidad | Ejemplos |
|--------|----------|----------|
| ✅ Resuelta | 4 | Exclusión de archivos locales en la imagen Docker · limpieza de la especificación · código del bot bajo control de versiones · autoría de commits vinculada al perfil |
| 🔜 Planificada | 1 | Tests automatizados y CI (HU-9.4, Sprint 5) |
| 📋 En backlog | 3 | Unificar la lista de categorías y el prompt entre bot y web · retirar código del prototipo inicial · ordenar carpetas locales |
| ⚖️ Aceptada | 1 | Borradores del bot no persistentes entre despliegues ([ADR-004](decisiones/ADR-004-railway-para-despliegue.md)) |
