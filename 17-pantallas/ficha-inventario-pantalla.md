**PLANTILLA PARA DILIGENCIAR · UNIDAD 6 · SESIÓN 2 DE 5**

**Ingeniería de Requisitos**

**Ficha de inventario de pantalla — SIGCortinas**

> **Nota de alcance.** Nivel de grupo de datos, no campo por campo (eso viene en las Sesiones 3 y 4). Once pantallas (P-01 a P-11) y dos mensajes (M-01, M-02), construidos a partir de `CU-01N.md` a `CU-10.md`, `srs-SIGcortinas.md`, `SIGCortinas-backlog-MoSCoW.md` y las personas de `ficha-persona-usuario.md` (PER-01 Empleada, PER-02 Gerente). El Técnico no tiene ficha de persona propia todavía (ver nota en `ficha-persona-usuario.md`); donde una pantalla es suya, se dice explícitamente que su diseño se apoya en inferencia del SRS, no en elicitación directa.

| Proyecto | Equipo | Versión del inventario | Fecha | Revisó (otro integrante) |
|---|---|---|---|---|
| SIGCortinas | Miguel Antonio Gómez Guío, Edward Steven Rocha Torres, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui | v0.1 | 20/11/2026 | Otro integrante del equipo |

## Tabla resumen del inventario

| ID | Pantalla | Etiqueta de menú | Zona · rol | CU · RF | MoSCoW · prototipo |
|---|---|---|---|---|---|
| **P-01** | Iniciar sesión | "Iniciar sesión" (sin menú: es la entrada) | Interna · Gerente, Empleada, Técnico | (transversal) · REQ-NF-02 | Must · ficha |
| **P-02** | Agenda del día | "Inicio" | Interna · Gerente, Empleada, Técnico (vista filtrada) | CU-03 · REQ-F-02, REQ-F-02a | Must · ficha |
| **P-03** | Nuevo pedido | "Nuevo pedido" | Interna · Empleada | CU-01N · REQ-F-04a, REQ-F-04b | Must · ficha |
| **P-04** | Agendar visita | "Agendar visita" | Interna · Empleada | CU-02 · REQ-F-01a, REQ-F-01b, REQ-F-01c | Must · ficha |
| **P-05** | Detalle de la visita | "sin menú: se llega desde P-02" | Interna · Gerente, Empleada, Técnico | CU-03, CU-04 · REQ-F-02, REQ-F-03 | Must · ficha |
| **P-06** | Registrar resultado | "sin menú: se llega desde P-05, solo Técnico" | Interna · Técnico | CU-10 · REQ-F-11 | Could · ficha |
| **P-07** | Registrar pago | "Registrar pago" | Interna · Empleada | CU-05 · (REQ-F-07 pendiente) | Should · ficha |
| **P-08** | Inventario | "Inventario" | Interna · Empleada, Gerente | CU-06 · REQ-F-06, REQ-NF-01 | Must · ficha |
| **P-09** | Ingreso de mercancía | "Ingreso de mercancía" | Interna · Gerente | CU-07 · (REQ-F-08 pendiente) | Should · ficha |
| **P-10** | Historial de clientes | "Historial de clientes" | Interna · Gerente, Empleada | CU-08 · REQ-NF-01 (REQ-F-09 pendiente) | Must · ficha |
| **P-11** | Garantías | "Garantías" | Interna · Gerente | CU-09 · REQ-F-10, REQ-NF-03 | Must · ficha |

*Todas las pantallas son de zona interna: SIGCortinas no tiene portal público (el cliente no accede al sistema, `acta-constitucion.md`, "Fuera de esta fase: acceso de clientes"). "Prototipo: ficha" indica que hoy solo existe esta ficha; el boceto o wireframe se hace en las Sesiones 3 y 4.*

## Tabla de mensajes

| ID | Disparador | Destinatario | Canal | Contenido mínimo | Qué pasa si falla el envío |
|---|---|---|---|---|---|
| **M-01** | Se confirma una nueva visita en P-04 (CU-02, paso 8) | Técnico asignado | Correo electrónico (`srs-SIGcortinas.md` §3.1.4) | Fecha, hora, dirección, tipo de visita y cliente | La cita queda guardada igual en la agenda compartida (P-02); el Técnico puede verla al entrar, aunque no reciba el correo — **pendiente:** decidir si se reintenta el envío o solo se deja constancia de que no llegó (hueco de diseño, Sesión 3). |
| **M-02** | Se confirma una reprogramación o cancelación en P-05 (CU-04, paso 8) | Técnico y Gerente | Correo electrónico (`srs-SIGcortinas.md` §3.1.4) | Cita afectada, nueva fecha u "Cancelada", motivo del cambio | Igual que M-01: la agenda compartida queda actualizada de todas formas; el aviso por correo es un refuerzo, no la única fuente de verdad. |

---

## Ficha de pantalla n.º 1 · ID y nombre: P-01 Iniciar sesión

| | |
|---|---|
| **Etiqueta de menú** | Sin menú: es la pantalla de entrada al sistema. |
| **Propósito** | Confirmar la identidad de la persona antes de dejarla entrar. |
| **Zona y rol(es)** | Interna · la ven los tres roles: Gerente, Empleada, Técnico. |
| **CU, requisitos e historia** | Transversal (ningún CU propio) · REQ-NF-02 · sin HU. |
| **Personas y tareas** | PER-01 (Empleada) y PER-02 (Gerente): entrar al sistema antes de cualquier tarea. Técnico: sin ficha de persona propia (pendiente, ver `ficha-persona-usuario.md`); se infiere la misma necesidad desde `srs-SIGcortinas.md` §2.1. |
| **Qué muestra (por grupo)** | Formulario de ingreso; mensaje de error si la credencial no es válida. |
| **Qué captura (por grupo)** | Usuario y contraseña. |
| **Acciones** | Iniciar sesión → lleva a P-02 (inicio del rol correspondiente). |
| **Viene de / lleva a** | Viene de: ninguna (es el punto de entrada). Lleva a: P-02. |
| **Estados de la pantalla** | Inicial; con error (credencial inválida); cargando. |
| **Mensajes** | Ninguno. |
| **Prioridad y prototipo** | Must (REQ-NF-02) · ficha. |
| **Preguntas abiertas** | ¿Hay recuperación de contraseña, o la restablece la Gerente manualmente al ser un equipo de tres personas? Responsable: Edward Rocha. Para cuándo: Sesión 3 de esta unidad. |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 2 · ID y nombre: P-02 Agenda del día

| | |
|---|---|
| **Etiqueta de menú** | "Inicio". |
| **Propósito** | Mostrar las actividades programadas de la fecha actual. |
| **Zona y rol(es)** | Interna · Gerente y Empleada (vista completa); Técnico (vista filtrada a sus propias visitas, CU-03 pasos 3-4). |
| **CU, requisitos e historia** | CU-03 · REQ-F-02, REQ-F-02a · HU-01, HU-02. |
| **Personas y tareas** | PER-01 (Empleada): tarea 2 de `contexto-uso-tareas.md` (agendar sin cruce, consultar el resultado aquí). PER-02 (Gerente): ver el panel sin perder ninguna cita (DOL-06 de `ficha-persona-usuario.md`). |
| **Qué muestra (por grupo)** | Listado de actividades del día (cliente, tipo, dirección, técnico, estado); alertas de citas "Por confirmar" (CU-03 ext. 2b) y de garantías con plazo excedido (CU-03 ext. 2c). |
| **Qué captura (por grupo)** | Filtro por técnico (CU-03, paso 3). No captura datos de negocio. |
| **Acciones** | Filtrar por técnico; abrir una actividad (lleva a P-05); ir a "Nuevo pedido" (P-03) o "Agendar visita" (P-04). |
| **Viene de / lleva a** | Viene de: P-01 (al iniciar sesión). Lleva a: P-05 [al abrir una actividad]; P-03, P-04 [desde el menú]. |
| **Estados de la pantalla** | Con actividades; vacía ("no hay actividades hoy", CU-03 ext. 2a, con la fecha de la próxima cita); con alertas (ext. 2b, 2c). |
| **Mensajes** | Ninguno disparado desde aquí (recibe el efecto de M-01 y M-02, pero no los envía). |
| **Prioridad y prototipo** | Must (HU-01, HU-02) · ficha. |
| **Preguntas abiertas** | ¿La vista filtrada del Técnico necesita un diseño más simple (menos columnas) por ser consultada desde el celular? Responsable: equipo, con validación pendiente con el Técnico (acción AM-01 de `autoevaluacion-capacidad.md`). Para cuándo: Sesión 3. |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 3 · ID y nombre: P-03 Nuevo pedido

| | |
|---|---|
| **Etiqueta de menú** | "Nuevo pedido". |
| **Propósito** | Registrar los datos de un pedido nuevo. |
| **Zona y rol(es)** | Interna · Empleada. |
| **CU, requisitos e historia** | CU-01N · REQ-F-04a, REQ-F-04b · (REQ-F-05, alcance futuro, pendiente — hueco H-01). |
| **Personas y tareas** | PER-01 (Empleada): tarea 1 de `contexto-uso-tareas.md` (registrar un pedido sin perder ningún dato; DOL-01, DOL-07, DOL-08). |
| **Qué muestra (por grupo)** | Datos del cliente (autocompletados si ya existe, CU-01N ext. 3a); resumen del pedido antes de confirmar. |
| **Qué captura (por grupo)** | Datos del cliente (nombre, teléfono); detalles del pedido (tipo, medidas/especificaciones, valor total, abono inicial). |
| **Acciones** | Buscar cliente existente; confirmar el pedido → lleva a P-02 con mensaje de confirmación y número de pedido. |
| **Viene de / lleva a** | Viene de: P-02 [menú]. Lleva a: P-02 [al confirmar]. |
| **Estados de la pantalla** | Inicial; con campos faltantes resaltados (ext. 6a); con abono inválido resaltado (ext. 6b); confirmado. |
| **Mensajes** | Ninguno. |
| **Prioridad y prototipo** | Must (CU-01N) · ficha. |
| **Preguntas abiertas** | REQ-F-05 (flujo completo de CU-01N) todavía no está detallado en `srs-SIGcortinas.md`: ¿esta misma pantalla alcanza, o hace falta una pantalla adicional? Responsable: Miguel Gómez. Para cuándo: inicio de Unidad 7 (H-01). |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 4 · ID y nombre: P-04 Agendar visita

| | |
|---|---|
| **Etiqueta de menú** | "Agendar visita". |
| **Propósito** | Programar una visita de medición o instalación. |
| **Zona y rol(es)** | Interna · Empleada. |
| **CU, requisitos e historia** | CU-02 · REQ-F-01a, REQ-F-01b, REQ-F-01c · HU-02 · (REQ-F-12, alcance futuro, pendiente — hueco H-05). |
| **Personas y tareas** | PER-01 (Empleada): tarea 2 de `contexto-uso-tareas.md` (DOL-02, DOL-09). |
| **Qué muestra (por grupo)** | Datos del cliente y su dirección; duración estimada según el tipo de visita; lista de técnicos disponibles; franjas libres si hay un cruce (ext. 6a). |
| **Qué captura (por grupo)** | Teléfono del cliente, tipo de visita, fecha y hora; técnico asignado y observaciones del trabajo. |
| **Acciones** | Seleccionar técnico; confirmar el agendamiento → envía M-01 y lleva a P-02. |
| **Viene de / lleva a** | Viene de: P-02 [menú]. Lleva a: P-02 [al confirmar]. |
| **Estados de la pantalla** | Inicial; con cliente nuevo (ext. 3a); con visita en finca, duración extendida (ext. 4a); con cruce de horario y alternativas (ext. 6a); confirmada. |
| **Mensajes** | M-01 (al confirmar). |
| **Prioridad y prototipo** | Must (HU-02) · ficha. |
| **Preguntas abiertas** | REQ-F-12 (flujo completo de agendamiento) sin detallar: ver H-05. Responsable: Miguel Gómez. Para cuándo: inicio de Unidad 7. |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 5 · ID y nombre: P-05 Detalle de la visita

| | |
|---|---|
| **Etiqueta de menú** | Sin menú: se llega desde P-02 (al abrir una actividad). |
| **Propósito** | Mostrar los datos completos de una visita agendada. |
| **Zona y rol(es)** | Interna · Gerente, Empleada (ven y, si es Empleada, puede reprogramar/cancelar); Técnico (ve y, si la visita es suya y de hoy, puede ir a P-06). |
| **CU, requisitos e historia** | CU-03 (detalle, pasos 5-6) y CU-04 (reprogramar/cancelar, como sección) · REQ-F-02, REQ-F-03 · sin HU propia. |
| **Personas y tareas** | PER-01 (Empleada): reprogramar o cancelar sin mantener agendas paralelas (DOL-02, DOL-09). Técnico: ver el detalle antes de ir a terreno (inferido, sin entrevista directa). |
| **Qué muestra (por grupo)** | Tipo de trabajo, medidas/especificaciones, observaciones, saldo pendiente del pedido; estado de la visita (Programada, Realizada, No realizada, Cancelada). |
| **Qué captura (por grupo)** | Nada por defecto. Si la Empleada elige reprogramar/cancelar (sección dentro de esta ficha, CU-04): nueva fecha/hora o motivo de cancelación. |
| **Acciones** | Reprogramar/cancelar (solo Empleada; abre la sección de CU-04, envía M-02 al confirmar); ir a registrar el resultado (solo Técnico, si la visita es de hoy y está "Programada" → lleva a P-06). |
| **Viene de / lleva a** | Viene de: P-02 [al abrir una actividad]. Lleva a: P-06 [Técnico, registrar resultado]; P-02 [al reprogramar/cancelar o al volver]. |
| **Estados de la pantalla** | Programada; reprogramada o cancelada (ext. 5a de CU-04); con motivo registrado; realizada o no realizada (reflejo de CU-10). |
| **Mensajes** | M-02 (al reprogramar o cancelar). |
| **Prioridad y prototipo** | Must (CU-03) · ficha. |
| **Preguntas abiertas** | ¿Qué tan atrás puede reprogramarse una cita (límite de horas antes de la visita)? Responsable: Gerente. Para cuándo: por confirmar, sin fecha límite escrita todavía (misma brecha G2 ya señalada en `autoevaluacion-capacidad.md`). |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 6 · ID y nombre: P-06 Registrar resultado

| | |
|---|---|
| **Etiqueta de menú** | Sin menú: se llega desde P-05, solo para el Técnico. |
| **Propósito** | Registrar el resultado de una visita ejecutada. |
| **Zona y rol(es)** | Interna · Técnico. |
| **CU, requisitos e historia** | CU-10 · REQ-F-11 · sin HU (prioridad Could). |
| **Personas y tareas** | Técnico: sin ficha de persona propia todavía (`ficha-persona-usuario.md`); el diseño de esta pantalla se apoya en `CU-10.md`, no en una entrevista directa — mismo pendiente señalado en la acción AM-01. |
| **Qué muestra (por grupo)** | Datos de la cita a registrar (cliente, tipo de trabajo esperado). |
| **Qué captura (por grupo)** | Medidas tomadas o confirmación de instalación; observaciones; hora de finalización; o, si el cliente no estaba, el motivo ("Cliente ausente", ext. 3a). |
| **Acciones** | Confirmar el registro → marca la visita "Realizada" (o "No realizada") y vuelve a P-05. |
| **Viene de / lleva a** | Viene de: P-05. Lleva a: P-05 [al confirmar]. |
| **Estados de la pantalla** | Inicial; con datos faltantes resaltados (ext. 6a); con medidas distintas a las registradas en el pedido (ext. 5a, alerta a la Gerente); "Cliente ausente" (ext. 3a); confirmada. |
| **Mensajes** | Ninguno (la notificación a la Empleada de CU-10, paso 8, es un aviso interno dentro del sistema, no un mensaje externo como M-01/M-02 — **por confirmar** si debería serlo). |
| **Prioridad y prototipo** | **Could** (CU-10, backlog MoSCoW) · ficha. |
| **Preguntas abiertas** | ¿El aviso a la Empleada para llamar al cliente (CU-10, paso 8) debería ser un mensaje con su propio ID (M-03), o basta con un estado visible en P-02? Responsable: equipo. Para cuándo: Sesión 3. |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 7 · ID y nombre: P-07 Registrar pago

| | |
|---|---|
| **Etiqueta de menú** | "Registrar pago". |
| **Propósito** | Registrar el pago del saldo pendiente de un pedido. |
| **Zona y rol(es)** | Interna · Empleada. |
| **CU, requisitos e historia** | CU-05 · (REQ-F-07, alcance futuro, pendiente — hueco H-02) · sin HU propia. |
| **Personas y tareas** | PER-01 (Empleada): cerrar el ciclo del pedido sin volver al cuaderno (inferido del hallazgo 6 de la entrevista, pago por mitades). |
| **Qué muestra (por grupo)** | Datos del pedido (total acordado, abonos registrados, saldo pendiente). |
| **Qué captura (por grupo)** | Número de pedido o teléfono del cliente; monto recibido y medio de pago. |
| **Acciones** | Buscar el pedido; confirmar el pago → genera el comprobante (descargable, Apéndice B del SRS). |
| **Viene de / lleva a** | Viene de: P-02 [menú]. Lleva a: P-02 [al confirmar, con mensaje de confirmación]. |
| **Estados de la pantalla** | Inicial; sin coincidencias (ext. 3a); sin saldo pendiente (ext. 4a); monto superior al saldo (ext. 6a); abono parcial (ext. 6b); pagado. |
| **Mensajes** | Ninguno. |
| **Prioridad y prototipo** | Should (CU-05, backlog MoSCoW) · ficha. |
| **Preguntas abiertas** | ¿El comprobante de pago se genera dentro de esta misma pantalla (acción "Descargar comprobante") o es un documento aparte? Responsable: Edward Rocha. Para cuándo: Sesión 3. REQ-F-07 sin detallar: ver H-02. |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 8 · ID y nombre: P-08 Inventario

| | |
|---|---|
| **Etiqueta de menú** | "Inventario". |
| **Propósito** | Consultar la existencia disponible de un artículo. |
| **Zona y rol(es)** | Interna · Empleada (consulta); Gerente (consulta y decide compras a partir de la alerta de existencia baja, ext. 6a — distinción pendiente de precisar en la Sesión 3, ver `lista-verificacion-pantallas.md`, ítem E3). |
| **CU, requisitos e historia** | CU-06 · REQ-F-06, REQ-NF-01 (desempeño, justificado) · sin HU propia. |
| **Personas y tareas** | PER-01 (Empleada): tarea 3 de `contexto-uso-tareas.md` (DOL-04, DOL-06). |
| **Qué muestra (por grupo)** | Artículos coincidentes con el criterio de búsqueda; detalle del artículo (existencia, unidad de medida, fecha de última actualización); alerta de existencia baja (ext. 6a) o "Agotado" (ext. 4b). |
| **Qué captura (por grupo)** | Criterio de búsqueda (nombre, referencia, tipo de tela o color). |
| **Acciones** | Buscar; seleccionar un artículo para ver su detalle. |
| **Viene de / lleva a** | Viene de: P-02 [menú]. Lleva a: ninguna (pantalla de consulta, sin flujo posterior). |
| **Estados de la pantalla** | Con resultados; sin resultados (ext. 4a); agotado (ext. 4b); con alerta de existencia baja (ext. 6a). |
| **Mensajes** | Ninguno. |
| **Prioridad y prototipo** | Must (CU-06) · ficha. |
| **Preguntas abiertas** | ¿La alerta de existencia baja debería disparar también una notificación a la Gerente, o basta con verla al consultar? Responsable: Gerente. Para cuándo: por confirmar. |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 9 · ID y nombre: P-09 Ingreso de mercancía

| | |
|---|---|
| **Etiqueta de menú** | "Ingreso de mercancía". |
| **Propósito** | Registrar la llegada de un pedido a la fábrica. |
| **Zona y rol(es)** | Interna · Gerente. |
| **CU, requisitos e historia** | CU-07 · (REQ-F-08, alcance futuro, pendiente — hueco H-03) · sin HU propia. |
| **Personas y tareas** | PER-02 (Gerente): tener un inventario real sin calcular "a ojo" (G2.2 del árbol de metas). |
| **Qué muestra (por grupo)** | Existencias actualizadas tras confirmar el ingreso. |
| **Qué captura (por grupo)** | Proveedor, fecha de recepción, referencia del pedido; artículos recibidos y su cantidad. |
| **Acciones** | Confirmar el ingreso → incrementa las existencias y lo guarda en el historial. |
| **Viene de / lleva a** | Viene de: P-02 [menú] o P-08 [acción "Registrar ingreso"]. Lleva a: P-08 [al confirmar, con existencias actualizadas]. |
| **Estados de la pantalla** | Inicial; con artículo nuevo que crear (ext. 5a); con cantidad inválida (ext. 6a); con referencia posiblemente duplicada (ext. 6b); cancelada antes de confirmar (ext. 7a); confirmada. |
| **Mensajes** | Ninguno. |
| **Prioridad y prototipo** | Should (CU-07, backlog MoSCoW) · ficha. |
| **Preguntas abiertas** | REQ-F-08 sin detallar: ver H-03. Responsable: Rafael Barriosnuevo. Para cuándo: inicio de Unidad 7. |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 10 · ID y nombre: P-10 Historial de clientes

| | |
|---|---|
| **Etiqueta de menú** | "Historial de clientes". |
| **Propósito** | Encontrar las compras y pedidos anteriores de un cliente. |
| **Zona y rol(es)** | Interna · Gerente (actor principal del CU); Empleada (consulta, interés documentado en CU-08, "informar al cliente el estado de su garantía"). |
| **CU, requisitos e historia** | CU-08 · REQ-NF-01 (desempeño, justificado) · (REQ-F-09, alcance futuro, pendiente — hueco H-04) · sin HU propia. |
| **Personas y tareas** | PER-02 (Gerente): tarea 3 de `contexto-uso-tareas.md` (DOL-06); PER-01 (Empleada), interés secundario. |
| **Qué muestra (por grupo)** | Lista de pedidos que cumplen los filtros (fecha, tipo, total, saldo, estado); detalle de un pedido (medidas, abonos, citas asociadas, garantías con días transcurridos). |
| **Qué captura (por grupo)** | Filtros de búsqueda (nombre o teléfono del cliente, rango de fechas, estado del pedido). |
| **Acciones** | Buscar; elegir entre varios clientes homónimos (ext. 3a); abrir el detalle de un pedido. |
| **Viene de / lleva a** | Viene de: P-02 [menú]. Lleva a: P-11 [si el pedido tiene una garantía abierta, ext. 6a]. |
| **Estados de la pantalla** | Con resultados; sin resultados (ext. 4a); paginada (ext. 4b); con homónimos (ext. 3a); con garantía abierta (ext. 6a). |
| **Mensajes** | Ninguno. |
| **Prioridad y prototipo** | Must (CU-08) · ficha. |
| **Preguntas abiertas** | REQ-F-09 (consulta histórica detallada) sin detallar: ver H-04. Responsable: Juan Chaparro. Para cuándo: inicio de Unidad 7. |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

## Ficha de pantalla n.º 11 · ID y nombre: P-11 Garantías

| | |
|---|---|
| **Etiqueta de menú** | "Garantías". |
| **Propósito** | Registrar una garantía enviada a la fábrica. |
| **Zona y rol(es)** | Interna · Gerente. |
| **CU, requisitos e historia** | CU-09 · REQ-F-10, REQ-NF-03 (conservación, justificado) · sin HU propia. |
| **Personas y tareas** | PER-02 (Gerente): controlar cada garantía sin perder de vista su plazo (G3.2 del árbol de metas). |
| **Qué muestra (por grupo)** | Pedido y artículo de origen; garantía existente con sus días transcurridos, si ya hay una abierta (ext. 6a). |
| **Qué captura (por grupo)** | Pedido y artículo; motivo, fecha de envío a la fábrica y referencia del caso en el portal de la fábrica. |
| **Acciones** | Confirmar el registro → crea la garantía en estado "En fábrica" y programa la alerta de plazo (reflejada en P-02). |
| **Viene de / lleva a** | Viene de: P-02 [menú] o P-10 [acción "Registrar garantía" desde el detalle de un pedido]. Lleva a: P-02 [al confirmar]. |
| **Estados de la pantalla** | Inicial; con pedido no registrado en el sistema, datos manuales (ext. 3a); con fecha de envío inválida (ext. 5a); con garantía ya abierta para el artículo (ext. 6a); confirmada. |
| **Mensajes** | Ninguno (la alerta de plazo excedido se ve como estado de P-02, no como mensaje externo). |
| **Prioridad y prototipo** | Must (CU-09) · ficha. |
| **Preguntas abiertas** | Ninguna pendiente distinta de las ya registradas en `catalogo-rnf.md` (plazo exacto de garantía, REQ-NF-03). |
| **Versión · revisó** | v0.1 · revisión de otro integrante del equipo (20/11/2026). |

---
