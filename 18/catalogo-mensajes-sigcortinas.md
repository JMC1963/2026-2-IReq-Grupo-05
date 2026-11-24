---
title: Catálogo de mensajes de interfaz — SIGCortinas
project: SIGCortinas
version: 0.1
date: 2026-11-24
---

# Catálogo de mensajes de interfaz — SIGCortinas

**Ingeniería de Requisitos · Unidad 6 · Sesión 3**

| Proyecto | Equipo | Versión | Fecha de elaboración | Revisión por par |
|---|---|---:|---|---|
| SIGCortinas | Miguel Antonio Gómez Guío, Edward Steven Rocha Torres, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui | v0.1 | 24/11/2026 | Pendiente de revisión por otro integrante del equipo |

## Criterios de redacción y alcance

Cada mensaje tiene un disparador identificable, texto literal, tipo, regla o requisito y canal. Se usan los IDs `MSG-nn` para mensajes de pantalla y se conservan `M-01` y `M-02` para correos automáticos ya identificados en el inventario de pantallas.

Los textos de esta versión se redactan desde los estados y reglas documentados para SIGCortinas. Cuando el proyecto no tiene un requisito explícito para un comportamiento de interfaz (por ejemplo, conservación del formulario cuando se pierde la conexión), se marca `PROP-UI-01` como propuesta por formalizar; **no se presenta como requisito ya aprobado**.

Reglas comunes:

- Lenguaje breve, respetuoso, en español y sin culpar a la persona.
- El error explica qué pasó y cómo corregirlo; se muestra junto al campo o en un resumen que enlaza al campo.
- Se conserva el dato digitado siempre que el comportamiento se implemente; para fallos de servicio o pérdida de conexión, la persistencia y la confirmación transaccional deben formalizarse.
- El color se acompaña de texto e icono.
- Los mensajes de éxito describen solo el resultado confirmado. El correo no se da por enviado hasta que el envío sea confirmado.

## Tabla de mensajes de pantalla

| ID | Pantalla o mensaje | Situación o disparador | Texto literal | Tipo | Regla o requisito | Canal |
|---|---|---|---|---|---|---|
| **MSG-01** | P-01 · Iniciar sesión | La persona intenta ingresar con credenciales que el sistema no acepta. | «No pudimos iniciar sesión con esos datos. Compruebe su usuario y contraseña e inténtelo de nuevo.» | Error | REQ-NF-02 (control de acceso por rol). El texto exacto y el tratamiento de intentos fallidos requieren revisión de seguridad; no se revela si el usuario o la contraseña fueron los incorrectos. | Pantalla |
| **MSG-02** | P-02 · Agenda del día | No existen actividades programadas para la fecha actual. | «No hay actividades programadas para hoy ({fecha}). La próxima visita está prevista para el {fecha_proxima}.» | Información | CU-03, extensión 2a · REQ-F-02. Si no existe una próxima visita, la alternativa textual debe confirmarse con el equipo. | Pantalla |
| **MSG-03** | P-02 · Agenda del día | Una cita del día no tiene registrada la confirmación previa con el cliente. | «Esta cita está pendiente de confirmación con el cliente.» | Advertencia | CU-03, extensión 2b · REQ-F-02a. El estado debe mostrarse con texto y símbolo, no solo color. | Pantalla |
| **MSG-04** | P-02 · Agenda del día | Una garantía enviada a fábrica supera 12 días transcurridos. | «La garantía {referencia_garantia} lleva {dias_transcurridos} días en fábrica: superó el plazo de 12 días. Revise su seguimiento.» | Advertencia | CU-03, extensión 2c · CU-09 · REQ-F-10. El plazo funcional de alerta está definido en el SRS; el plazo legal total de garantía sigue pendiente de confirmación. | Pantalla |
| **MSG-05** | P-02 · Agenda del día | No se puede cargar o actualizar la agenda por un fallo del servicio. | «No pudimos actualizar la agenda. Compruebe la conexión e inténtelo de nuevo.» | Error | Estado de error de servicio exigido por la guía. Propuesta `PROP-UI-01` por formalizar; el SRS supone conectividad, pero no define el texto ni el comportamiento exacto del error de carga. | Pantalla |
| **MSG-06** | P-03 · Nuevo pedido | La Empleada intenta guardar el pedido y falta uno o más campos obligatorios. | «Complete el campo {nombre_campo}; es obligatorio para guardar el pedido.» | Error | REQ-F-04a y Apéndice B del SRS. Mostrar junto a cada campo faltante y en un resumen cuando haya varios. | Pantalla |
| **MSG-07** | P-03 · Nuevo pedido | El abono inicial no corresponde al 50 % del valor total. | «El abono inicial debe ser el 50 % del valor total. Para un total de {valor_total}, registre {abono_requerido}.» | Error | REQ-F-04b. La regla de 50 % redondeado al peso superior permanece pendiente de ratificación de la Gerente (decisión D-02). | Pantalla |
| **MSG-08** | P-03 · Nuevo pedido | La persona necesita conocer la regla del abono antes de confirmar. | «El abono inicial corresponde al 50 % del valor total, redondeado al peso superior.» | Ayuda | REQ-F-04b · Apéndice B del SRS. Mantener visible junto al campo del abono; confirmar la regla comercial mediante D-02. | Pantalla |
| **MSG-09** | P-03 · Nuevo pedido | El sistema confirma el registro del pedido y dispone de su número. | «Pedido {numero_pedido} registrado.» | Éxito | CU-01N e inventario P-03: al confirmar, regresar a P-02 con mensaje y número de pedido. El formato del número no está definido en los archivos revisados. | Pantalla |
| **MSG-10** | P-03 · Nuevo pedido | Falla el servicio o no se recibe confirmación al guardar el pedido. | «No recibimos confirmación del registro del pedido. Mantenga esta pantalla abierta y compruebe si el pedido quedó guardado antes de enviarlo otra vez. Los datos que escribió siguen visibles aquí.» | Error | Estado de error de servicio de la guía. Propuesta `PROP-UI-01` por formalizar: conservación del formulario y prevención de duplicados ante una respuesta incierta. No existe un requisito explícito de microcopy para este escenario. | Pantalla |
| **MSG-11** | P-04 · Agendar visita / P-05 · Detalle de la visita | La franja solicitada se superpone con otra cita programada del mismo Técnico. | «El Técnico ya tiene una visita entre {hora_inicio} y {hora_fin}. Elija una franja libre de igual duración.» | Error | REQ-F-01a y REQ-F-03; Apéndice B: validación compartida de disponibilidad. En P-04 mostrar alternativas libres de igual duración dentro de los próximos siete días, cuando existan. | Pantalla |
| **MSG-12** | P-04 · Agendar visita | No hay franjas libres de igual duración en los próximos siete días. | «No hay una franja libre de {duracion} para el Técnico en los próximos siete días. Proponga otra fecha para continuar.» | Información | REQ-F-01a · CU-02, extensión 6a. No sugerir un Técnico alternativo: el proyecto no documenta una lista de técnicos disponibles múltiples. | Pantalla |
| **MSG-13** | P-04 · Agendar visita | El sistema calcula la duración estimada de la visita seleccionada. | «La duración estimada de esta visita es de {duracion}.» | Información | REQ-F-01c. En visitas a finca se calcula 4 u 8 horas según la distancia al local. El caso exacto de una distancia de 30 minutos queda pendiente de aclaración. | Pantalla |
| **MSG-14** | P-04 · Agendar visita | La visita queda confirmada y publicada en la agenda compartida. | «Visita agendada para el {fecha} a las {hora}. La agenda compartida ya está actualizada.» | Éxito | CU-02 · REQ-F-01a, REQ-F-01b y REQ-F-01c. No afirma que M-01 fue enviado; el estado del correo se informa por separado. | Pantalla |
| **MSG-15** | P-04 · Agendar visita | No se puede comprobar la disponibilidad o confirmar el agendamiento por un fallo del servicio. | «No recibimos confirmación del agendamiento. Consulte la agenda compartida antes de registrar la visita otra vez.» | Error | Estado de error de servicio de la guía y REQ-NF-09 (conexión móvil intermitente como necesidad por validar). Propuesta `PROP-UI-01` por formalizar. | Pantalla |
| **MSG-16** | P-05 · Detalle de la visita | La Empleada intenta reprogramar una cita a una fecha anterior al momento actual. | «La nueva fecha no puede ser anterior al momento actual. Elija una fecha y hora actuales o futuras.» | Error | REQ-F-03: se rechaza una nueva fecha anterior al momento actual. | Pantalla |
| **MSG-17** | P-05 · Detalle de la visita | La reprogramación queda guardada correctamente. | «La visita se reprogramó para el {nueva_fecha} a las {nueva_hora}. El motivo quedó registrado y la agenda compartida se actualizó.» | Éxito | REQ-F-03. El sistema también genera M-02 para el Técnico y la Gerente. | Pantalla |
| **MSG-18** | P-05 · Detalle de la visita | La cancelación queda guardada correctamente. | «La visita fue cancelada. El motivo quedó registrado y la agenda compartida se actualizó.» | Éxito | REQ-F-03. El sistema también genera M-02 para el Técnico y la Gerente. | Pantalla |
| **MSG-19** | P-08 · Inventario | La búsqueda no encuentra artículos que coincidan con el criterio. | «No encontramos artículos con “{criterio}”. Revise el nombre, la referencia, el tipo de tela o el color e inténtelo de nuevo.» | Información | CU-06 · REQ-F-06. Los criterios de búsqueda están identificados en la ficha P-08. | Pantalla |
| **MSG-20** | P-08 · Inventario | La existencia registrada de un artículo es cero. | «El artículo {nombre_articulo} no tiene existencias disponibles. Estado: Agotado.» | Advertencia | CU-06, extensión 4b · REQ-F-06. Acompañar «Agotado» de símbolo y texto. | Pantalla |
| **MSG-21** | P-11 · Garantías | Se intenta registrar una garantía para un artículo que ya tiene una garantía abierta. | «Ya existe una garantía abierta para este artículo. Revise el registro existente antes de crear otra.» | Error | CU-09, extensión 6a · REQ-F-10. | Pantalla |
| **MSG-22** | Todas las pantallas con control de acceso | Un rol intenta acceder a una pantalla o acción que no tiene autorizada. | «Su rol no tiene permiso para acceder a esta función.» | Error | REQ-NF-02. La autorización debe verificarse en el servidor; ocultar una opción del menú no sustituye el control de acceso. | Pantalla |
| **MSG-23** | P-02, P-03 y P-04 · Estado sin conexión | Se pierde la conexión y el sistema no recibe confirmación de la operación. | «Se perdió la conexión y no recibimos confirmación de {operacion}. Compruebe el estado del registro antes de enviarlo otra vez.» | Error | REQ-NF-09 (conexión móvil intermitente, valor por validar) + propuesta `PROP-UI-01` sobre confirmación y conservación de datos. El comportamiento exacto debe especificarse y probarse; no se asume guardado sin confirmación. | Pantalla |

**Total:** 23 mensajes de pantalla (`MSG-01` a `MSG-23`), más dos mensajes de correo (`M-01` y `M-02`) descritos a continuación.

## Mensajes por correo (M-nn): asunto y cuerpo

### M-01 · Nueva visita agendada

| Campo | Contenido |
|---|---|
| Destinatario | Técnico asignado. |
| Disparador | La Empleada confirma una nueva visita en P-04 (CU-02, paso 8). |
| Canal | Correo electrónico. |
| Asunto | `Nueva visita agendada: {fecha} a las {hora}` |
| Cuerpo | `Hola, {nombre_tecnico}. Se agendó una visita de {tipo_visita} para el {fecha} a las {hora}, en {direccion}. Cliente: {nombre_cliente}. Consulte los detalles en la agenda de SIGCortinas. Este es un mensaje automático; la agenda compartida del sistema es la referencia principal de la cita.` |
| Regla / requisito | CU-02, paso 8 · SRS §3.1.4 · REQ-F-01a/01b/01c. El contenido mínimo (fecha, hora, dirección, tipo de visita y cliente) está definido en el inventario P-04. |
| Si falla el envío | La cita permanece guardada en P-02. El Técnico puede verla al entrar al sistema. **Pendiente:** decidir si se reintenta el envío o solo se deja constancia del fallo. No se revierte la cita por un fallo de correo. |

### M-02 · Reprogramación o cancelación de cita

| Campo | Contenido |
|---|---|
| Destinatario | Técnico y Gerente. |
| Disparador | La Empleada confirma una reprogramación o cancelación en P-05 (CU-04, paso 8). |
| Canal | Correo electrónico. |
| Asunto | `Cambio de cita: {fecha_anterior} · {estado_cambio}` |
| Cuerpo | `Hola. La visita de {nombre_cliente}, prevista para el {fecha_anterior} a las {hora_anterior}, fue {reprogramada/cancelada}. {detalle_nueva_fecha_si_aplica} Motivo registrado: {motivo}. La agenda compartida de SIGCortinas ya fue actualizada. Consulte P-02 para ver el estado actual de la cita. Este es un mensaje automático.` |
| Regla / requisito | CU-04, paso 8 · SRS §3.1.4 · REQ-F-03. La agenda compartida se actualiza, se registra el motivo y se notifica al Técnico y a la Gerente. |
| Si falla el envío | La actualización de la agenda se mantiene; el correo es un refuerzo, no la única fuente de verdad. **Pendiente:** definir reintento o registro de fallo. |

## Mensajes y decisiones pendientes

| ID / tema | Qué falta decidir o verificar | Responsable indicado por el proyecto | Estado |
|---|---|---|---|
| `PROP-UI-01` | Formalizar qué datos permanecen en pantalla ante fallo de servicio o pérdida de conexión, cómo se distingue «no enviado» de «resultado no confirmado» y cómo se evita un doble registro. | Equipo de desarrollo; responsable individual por asignar. | Propuesta, no requisito aprobado. |
| `MSG-01` | Confirmar políticas de intentos fallidos y recuperación de contraseña. | Equipo / Gerente; la recuperación de contraseña aparece como pregunta abierta de P-01. | Pendiente. |
| `MSG-07` / `MSG-08` | Ratificar el 50 % de abono inicial y el redondeo al peso superior. | Gerente (Vicky Beltrán), decisión D-02. | Pendiente. |
| `MSG-09` | Definir formato del número de pedido que sustituye `{numero_pedido}`. | Miguel Antonio Gómez Guío, en el desarrollo de REQ-F-05 / H-01. | Pendiente de Unidad 7. |
| `MSG-13` | Aclarar cómo se calcula la duración para una finca ubicada exactamente a 30 minutos del local. | Gerente / equipo, regla comercial. | Pendiente. |
| `M-01` / `M-02` | Definir reintentos, registro de fallos de correo y tratamiento de direcciones/datos personales. | Equipo y Gerente; validar privacidad. | Pendiente. |
| `M-03` | Decidir si el aviso a la Empleada cuando el Técnico registra el resultado de una visita (CU-10, paso 8) será un mensaje interno con ID propio o solo un estado en P-02. | Equipo de desarrollo. | No se crea un ID definitivo porque la ficha P-06 lo deja expresamente por confirmar. |

## Fuentes del proyecto usadas

- `17-pantallas/ficha-inventario-pantalla.md` — estados, datos y acciones por pantalla; M-01 y M-02; preguntas abiertas.
- `17-pantallas/matriz-trazabilidad-pantallas.md` — trazabilidad CU ↔ pantalla ↔ requisito y huecos.
- `7-srs/srs-sigcortinas.md` — reglas REQ-F-01a/b/c, REQ-F-02/02a, REQ-F-03, REQ-F-04a/b, REQ-F-06, REQ-F-10, REQ-NF-02 y Apéndice B.
- `16-usuarios-usabilidad/requisitos-usabilidad-accesibilidad.md` — REQ-NF-08 y REQ-NF-09.
- Guía adjunta, sección 5 — microcopy, errores, correos y requisitos del catálogo.
