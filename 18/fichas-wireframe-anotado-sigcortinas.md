---
title: Fichas de wireframe anotado — SIGCortinas
project: SIGCortinas
version: 0.1
date: 2026-11-24
---

# Fichas de wireframe anotado — SIGCortinas

**Ingeniería de Requisitos · Unidad 6 · Sesión 3**

| Proyecto | Equipo | Versión | Fecha de elaboración | Revisión por par |
|---|---|---:|---|---|
| SIGCortinas | Miguel Antonio Gómez Guío, Edward Steven Rocha Torres, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui | v0.1 | 24/11/2026 | Pendiente de revisión por otro integrante del equipo |

## Selección de las tres pantallas críticas

La guía pide priorizar por frecuencia de uso, riesgo si la pantalla falla, experiencia de las personas usuarias y cantidad de requisitos relacionados. La selección se basa en las tareas documentadas en `16-usuarios-usabilidad/contexto-uso-tareas.md`, el inventario P-01 a P-11 y la matriz de trazabilidad.

| Orden | Pantalla | Evidencia de frecuencia / contexto | Riesgo documentado | Usuario principal | Requisitos / prioridad | Decisión |
|---:|---|---|---|---|---|---|
| 1 | **P-03 · Nuevo pedido** | La tarea «Registrar un pedido nuevo» ocurre varias veces al día; la entrevista menciona 4–5 instalaciones en un buen día. | Alta: un dato omitido o mal anotado puede dejar el pedido incompleto o causar que el Técnico llegue sin información; la Empleada ha olvidado datos alguna vez. | Empleada (PER-01), usuaria primaria y sin entrenamiento previo en sistemas. | REQ-F-04a y REQ-F-04b; CU-01N; Must. REQ-NF-07.1 como objetivo de usabilidad por validar. | Se selecciona por frecuencia diaria, criticidad alta y relación directa con la persona mejor documentada. |
| 2 | **P-04 · Agendar visita** | La tarea se presenta varias veces por semana; la entrevista recoge 10, 8 y 5 visitas según el mes, pero el dato no está definido con precisión. | Alta: un cruce puede impedir que el Técnico cumpla una de las visitas o hacer que el cliente espere en vano. | Empleada (PER-01). El Técnico es destinatario y usuario móvil, pero no tiene entrevista propia. | REQ-F-01a, REQ-F-01b y REQ-F-01c; CU-02; Must. REQ-NF-07.2. | Se selecciona porque una falla tiene consecuencia operativa y comercial alta y hay tres requisitos Must. |
| 3 | **P-02 · Agenda del día** | Es la pantalla de inicio de los tres roles y la consulta central de las actividades programadas para la fecha actual. El proyecto no aporta un conteo de aperturas. | Alta por el impacto de no detectar citas, cambios, citas «Por confirmar» o garantías con plazo excedido. La vista del Técnico es filtrada a sus propias visitas. | Gerente, Empleada y Técnico; para el Técnico la vista móvil se basa todavía en inferencia del SRS. | REQ-F-02 y REQ-F-02a; CU-03; Must; HU-01/HU-02 relacionadas. REQ-NF-09 para la adaptación móvil a validar. | Se selecciona como centro operativo diario y punto de entrada a los flujos de P-03 y P-04. |

**Por qué no se eligió P-08/P-10 en esta primera tanda:** la consulta de inventario e historial también es importante y tiene un umbral de ≤ 60 segundos (REQ-NF-07.3), pero la frecuencia no está cuantificada en la evidencia y el flujo de historial (REQ-F-09) está pendiente de especificación. P-02 se prioriza aquí por ser el inicio compartido y sostener la agenda de los tres roles. Esta decisión puede revisarse tras validar con Gerente y Técnico.

> **Alcance del material gráfico:** como el entregable solicitado es Markdown y el ZIP del proyecto no contiene wireframes HTML/PNG para estas pantallas, los dibujos siguientes son **bocetos textuales de baja fidelidad** con marcas numeradas. No son capturas ni prototipos ya probados. La herramienta final (kit HTML del curso, draw.io, Penpot u otra) y los archivos PNG quedan pendientes de producir y versionar.

---

# Ficha WF-P02 · Agenda del día

| Campo | Valor |
|---|---|
| ID del wireframe | **WF-P02** |
| Pantalla (nombre exacto del inventario) | **P-02 · Agenda del día** |
| Versión / fecha | v0.1 · 24/11/2026 |
| Dibujó | Equipo SIGCortinas (boceto textual de esta entrega) |
| Revisó | Pendiente de revisión por otro integrante y validación con usuarios |
| Rol(es) | Gerente y Empleada: agenda completa. Técnico: agenda filtrada a sus propias visitas. |
| Caso(s) / requisito(s) | CU-03 · REQ-F-02 · REQ-F-02a · REQ-F-10 (alerta de garantía en panel) · REQ-NF-02 · REQ-NF-09 (móvil, por validar). |
| Resolución representada | Escritorio: 1280 px como lienzo de trabajo propuesto, no como requisito medido. Vista móvil del Técnico: referencia de 360 px (REQ-NF-09, valor por validar). |
| Herramienta | Boceto textual en Markdown; no existe aún fuente HTML ni imagen PNG. |

## 1. Wireframe (estado inicial)

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ SIGCortinas                                      [Usuario] [Cerrar sesión] │
│                                                                             │
│ Agenda del día · {fecha actual}                                             │
│                                                                             │
│ [1] Filtro por Técnico: [Todos / {Técnico}]                                 │
│                                                                             │
│ [2] ALERTAS                                                                  │
│     [!] Por confirmar: {n} citas                                             │
│     [!] Plazo excedido: {n} garantías                                       │
│                                                                             │
│ [3] Actividades de hoy (ordenadas por hora)                                 │
│ ┌────────┬─────────────┬───────────┬────────────┬───────────┬─────────────┐ │
│ │ Hora   │ Cliente     │ Tipo      │ Dirección  │ Técnico   │ Estado      │ │
│ ├────────┼─────────────┼───────────┼────────────┼───────────┼─────────────┤ │
│ │ {hora} │ {cliente}   │ {tipo}    │ {dir.}     │ {técnico} │ {estado}    │ │
│ │ {hora} │ {cliente}   │ {tipo}    │ {dir.}     │ {técnico} │ {estado}    │ │
│ └────────┴─────────────┴───────────┴────────────┴───────────┴─────────────┘ │
│                                                                             │
│ [4] Seleccionar una actividad para abrir su detalle                         │
│                                                                             │
│ [5] Accesos principales: [Nuevo pedido] [Agendar visita]                    │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Vista móvil del Técnico (esquema responsive, no imagen):** una columna con fecha, alertas y tarjetas de sus propias visitas ordenadas por hora; cada tarjeta muestra cliente, tipo, hora, dirección y estado, y abre P-05. La lista no muestra la agenda de otros Técnicos. La composición final debe probarse a 360 px y con conexión móvil real.

## 2. Tabla de anotaciones

| N.º | Elemento | Comportamiento o regla | Requisito |
|---:|---|---|---|
| 1 | Filtro por Técnico | Gerente y Empleada consultan la agenda completa; el Técnico ve sus propias visitas. La selección filtra las actividades del día. | CU-03, pasos 3–4; REQ-NF-02. |
| 2 | Alertas «Por confirmar» | Las citas sin confirmación previa deben quedar identificadas por texto y símbolo. No depender solo del color. | CU-03, extensión 2b; REQ-F-02a; REQ-NF-08. |
| 3 | Alertas de garantía | Mostrar «Plazo excedido» cuando han transcurrido más de 12 días desde el envío a fábrica. Incluir texto y símbolo. | CU-03, extensión 2c; CU-09; REQ-F-10; REQ-NF-08. |
| 4 | Tabla de actividades | Ordenar por hora y mostrar cliente, tipo de visita, dirección, Técnico y estado. Actualizar tras creación, reprogramación o cancelación cuando se vuelva a abrir o recargar la agenda. | REQ-F-02. |
| 5 | Fila / abrir detalle | Al seleccionar una actividad se abre P-05. El detalle y las acciones deben respetar el rol. | CU-03; matriz de trazabilidad, Dirección B; REQ-NF-02. |
| 6 | Acceso «Nuevo pedido» | Lleva a P-03 para la Empleada autorizada. | Inventario P-02/P-03; CU-01N; REQ-F-04a/04b; REQ-NF-02. |
| 7 | Acceso «Agendar visita» | Lleva a P-04 para la Empleada autorizada. | Inventario P-02/P-04; CU-02; REQ-F-01a/01b/01c; REQ-NF-02. |
| 8 | Vista móvil del Técnico | Mostrar únicamente sus propias visitas en una columna; no diseñar un portal público ni una app nativa. | SRS §2.1; REQ-NF-09 (360 px propuesto, conexión intermitente por validar). |

## 3. Estados de la pantalla

| Estado | Qué se ve | Qué se conserva de lo digitado | Mensaje (ID) |
|---|---|---|---|
| Inicial | Fecha actual, filtro permitido por rol, alertas y tabla de actividades ordenadas por hora. | No hay formulario de captura; conservar el filtro elegido durante la navegación es una decisión de interfaz propuesta. | — |
| Vacío | «No hay actividades programadas para hoy» y fecha de la próxima visita, si existe. | No aplica; no hay datos de formulario. | MSG-02 |
| Cargando | Indicador «Cargando agenda…»; evitar mostrar datos antiguos como si fueran actuales. | Mantener el filtro seleccionado. | — |
| Con errores de validación | No aplica como estado principal: la pantalla no captura datos de negocio. El filtro por Técnico no tiene reglas de formato documentadas. | No aplica. | — |
| Error de servicio | Aviso de que la agenda no pudo actualizarse; no presentar datos obsoletos como actuales. | Mantener filtro. Si se muestra una última carga disponible, debe identificarse como no actual; ese comportamiento está por definir. | MSG-05 |
| Éxito | Agenda cargada / actualizada; la tabla refleja citas de la fecha. No se requiere un toast adicional por abrir el panel. | Mantener filtro seleccionado. | — |
| Sin permiso | Los tres roles del inventario tienen acceso a P-02; se niega el acceso a roles no autorizados o acciones no permitidas. | No aplica. | MSG-22 |
| Sin conexión | Indicar que no se recibió actualización. No marcar como actual la agenda cacheada; el manejo de caché está pendiente. | Mantener el filtro de la sesión cuando sea posible. | MSG-23 |

## 4. Pendientes y preguntas abiertas

| ID | Qué falta decidir | Quién lo resuelve | Para cuándo |
|---|---|---|---|
| P02-01 | Confirmar con el Técnico si la vista móvil necesita menos columnas y validar el uso real del navegador, teléfono y señal en campo. | Juan Miguel Chaparro coordina las entrevistas del Técnico (AM-01); equipo de desarrollo diseña. | 28/11/2026 (acción AM-01). |
| P02-02 | Definir cómo se presenta la última agenda cargada cuando falla la actualización y cómo se informa su antigüedad. | Equipo de desarrollo. | Antes de cerrar el prototipo de Sesión 4. |
| P02-03 | Probar teclado, foco, contraste y ampliación; la lista de comprobación del proyecto señala que el diseño todavía no se ha probado. | Equipo de desarrollo; revisión por otro integrante. | Sesión 4–5. |
| P02-04 | Realizar revisión con dos o tres usuarios del perfil real y documentar hallazgos. La evidencia disponible no acredita que esta revisión ya se haya realizado. | Equipo SIGCortinas; disponibilidad de Gerente, Empleada y Técnico. | Antes de cerrar la Sesión 3. |

---

# Ficha WF-P03 · Nuevo pedido

| Campo | Valor |
|---|---|
| ID del wireframe | **WF-P03** |
| Pantalla (nombre exacto del inventario) | **P-03 · Nuevo pedido** |
| Versión / fecha | v0.1 · 24/11/2026 |
| Dibujó | Equipo SIGCortinas (boceto textual de esta entrega) |
| Revisó | Pendiente de revisión por otro integrante y validación con usuarios |
| Rol(es) | Empleada. Otros roles no deben ejecutar esta operación. |
| Caso(s) / requisito(s) | CU-01N · REQ-F-04a · REQ-F-04b · REQ-NF-04 · REQ-NF-07.1 (umbral por validar) · REQ-NF-02. REQ-F-05 es alcance futuro pendiente. |
| Resolución representada | Escritorio: 1280 px como lienzo de trabajo propuesto; confirmar equipo real del local. No hay requisito de portal público para esta pantalla. |
| Herramienta | Boceto textual en Markdown; no existe aún fuente HTML ni imagen PNG. |

## 1. Wireframe (estado inicial)

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ SIGCortinas  /  Nuevo pedido                                                │
│                                                                             │
│ [1] DATOS DEL CLIENTE                                                       │
│     Nombre completo:  [____________________________________]               │
│     Teléfono:         [____________________________________]               │
│     [Buscar cliente existente]                                              │
│                                                                             │
│ [2] DATOS DEL PEDIDO                                                        │
│     Tipo de producto / servicio: [________________________v]               │
│     Medidas y especificaciones:  [__________________________]               │
│                                  [__________________________]               │
│                                                                             │
│ [3] VALOR Y ABONO                                                           │
│     Valor total:       [$_______________________________]                  │
│     Abono inicial:     [$_______________________________]                  │
│     Ayuda: 50 % del valor total, redondeado al peso superior.               │
│                                                                             │
│ [4] Resumen del pedido                                                     │
│     Cliente · tipo · medidas · valor total · abono inicial                 │
│                                                                             │
│ [5] Resumen de errores (solo cuando corresponda)                           │
│     [!] Hay {n} campos obligatorios pendientes.                            │
│                                                                             │
│ [6]                         [Confirmar pedido]                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 2. Tabla de anotaciones

| N.º | Elemento | Comportamiento o regla | Requisito |
|---:|---|---|---|
| 1 | Nombre y teléfono del cliente | Son campos obligatorios. Si falta uno, identificar ese campo junto a su etiqueta; no basta con un borde de color. | REQ-F-04a; Apéndice B del SRS. |
| 2 | Tipo de producto/servicio | Campo obligatorio. Usar la terminología del negocio; las opciones exactas del selector deben confirmarse con el catálogo real. | REQ-F-04a; Apéndice B. |
| 3 | Medidas y especificaciones | Campo obligatorio para que el Técnico reciba la información necesaria. El formato y longitud no están especificados en los archivos revisados; no imponer máscara todavía. | REQ-F-04a; CU-01N. |
| 4 | Valor total | Debe ser positivo y obligatorio. El mensaje de validación debe identificar el valor no aceptado; reglas de formato monetario se deben fijar en la especificación detallada. | REQ-F-04a; Apéndice B. |
| 5 | Abono inicial | Debe corresponder al 50 % del valor total, redondeado al peso superior. La cifra se valida antes de guardar; D-02 requiere ratificación de la Gerente. | REQ-F-04b; decisión D-02. |
| 6 | Buscar cliente existente | Permite autocompletar los datos si el cliente ya existe. La interacción exacta cuando no hay coincidencias debe aclararse antes de cerrar el prototipo. | CU-01N, extensión 3a; inventario P-03. |
| 7 | Resumen del pedido | Presentar los datos antes de la acción final para que la Empleada pueda comprobarlos. | Inventario P-03; CU-01N. |
| 8 | Acción primaria «Confirmar pedido» | Una sola acción primaria, con verbo + objeto. Si falta un campo, se rechaza la operación e identifica cada campo faltante. | REQ-F-04a/04b. |
| 9 | Confirmación con número de pedido | Tras el registro exitoso, volver a P-02 e informar el número de pedido. El patrón/formato del número está pendiente. | CU-01N e inventario P-03; REQ-F-05 pendiente de detalle (H-01). |
| 10 | Mensajes de error y conservación | Mostrar error junto al campo y conservar datos. La conservación ante fallo de servicio o pérdida de conexión necesita criterio explícito adicional. | REQ-F-04a/04b; `PROP-UI-01` pendiente para servicio/sin conexión. |

## 3. Estados de la pantalla

| Estado | Qué se ve | Qué se conserva de lo digitado | Mensaje (ID) |
|---|---|---|---|
| Inicial | Formulario vacío con secciones de cliente, pedido y valor/abono; etiquetas y ayudas visibles. | Nada todavía. | MSG-08 (ayuda del abono, siempre visible bajo el campo). |
| Vacío | No se define una pantalla de resultados vacía separada. El formulario sin datos corresponde al estado inicial. La búsqueda de cliente sin coincidencias requiere definir si se permite continuar con un cliente nuevo. | No aplica a una pantalla de lista; conservar el criterio de búsqueda mientras se resuelve la decisión. | Pendiente; no se asigna un ID hasta definir la regla de cliente nuevo. |
| Cargando | Indicador al buscar un cliente existente o enviar el pedido; evitar doble envío. | Mantener los campos que ya fueron diligenciados. | — |
| Con errores de validación | Resumen enlazado a los campos faltantes; mensaje bajo cada campo obligatorio omitido; mensaje específico si el abono no es el 50 % del total. | Conservar todos los valores ya digitados; corregir un campo no borra los demás. | MSG-06, MSG-07 |
| Error de servicio | Aviso de que no se recibió confirmación del registro; mantener visible el formulario y evitar un segundo envío hasta comprobar el estado. Este comportamiento es una propuesta pendiente de formalizar. | Los valores deben permanecer visibles según `PROP-UI-01`; aún no está aprobado ni probado. | MSG-10 |
| Éxito | Confirmación «Pedido {numero_pedido} registrado» y retorno a P-02. | La confirmación muestra el número; el formulario ya no necesita permanecer editable tras confirmar. | MSG-09 |
| Sin permiso | Si accede un rol distinto de Empleada, el servidor deniega la operación conforme al control de acceso por rol. | No conservar datos de una operación no autorizada. | MSG-22 |
| Sin conexión | Mostrar que no se recibió confirmación; no asumir ni afirmar que el pedido se guardó. La persona debe verificar antes de repetir. | Conservar valores del formulario es la decisión propuesta, pendiente de formalizar y probar. | MSG-23 |

## 4. Pendientes y preguntas abiertas

| ID | Qué falta decidir | Quién lo resuelve | Para cuándo |
|---|---|---|---|
| P03-01 | Completar el flujo de creación de pedido (REQ-F-05) y decidir si P-03 cubre todo o se requiere otra pantalla. | Miguel Antonio Gómez Guío (H-01). | Inicio de Unidad 7. |
| P03-02 | Ratificar el 50 % de abono inicial y la regla de redondeo. | Gerente (Vicky Beltrán), decisión D-02. | Antes de congelar el requisito y el prototipo. |
| P03-03 | Definir el resultado de «Buscar cliente» cuando no existen coincidencias, incluidos campos y acción para cliente nuevo. | Equipo; validar con Gerente y Empleada. | Sesión 3–4. |
| P03-04 | Definir el formato del número de pedido y comprobar si se requiere mensaje/documento adicional. | Miguel Antonio Gómez Guío (H-01) y equipo. | Unidad 7. |
| P03-05 | Formalizar la retención de datos y la prevención de duplicados cuando falla el servicio o la conexión (`PROP-UI-01`). | Equipo de desarrollo. | Antes de implementar el guardado. |
| P03-06 | Medir la línea base de tiempo de registro en el cuaderno y validar el umbral de REQ-NF-07.1 con PER-01. | Equipo con la Empleada (Milena Bermúdez). | Sesión 5. |

---

# Ficha WF-P04 · Agendar visita

| Campo | Valor |
|---|---|
| ID del wireframe | **WF-P04** |
| Pantalla (nombre exacto del inventario) | **P-04 · Agendar visita** |
| Versión / fecha | v0.1 · 24/11/2026 |
| Dibujó | Equipo SIGCortinas (boceto textual de esta entrega) |
| Revisó | Pendiente de revisión por otro integrante y validación con usuarios |
| Rol(es) | Empleada. El Técnico recibe la notificación M-01 y consulta su agenda. |
| Caso(s) / requisito(s) | CU-02 · REQ-F-01a · REQ-F-01b · REQ-F-01c · REQ-NF-07.2 · REQ-NF-02. REQ-F-12 es alcance futuro pendiente. |
| Resolución representada | Escritorio: 1280 px como lienzo de trabajo propuesto; confirmar equipo real del local. No hay requisito de portal público para esta pantalla. |
| Herramienta | Boceto textual en Markdown; no existe aún fuente HTML ni imagen PNG. |

## 1. Wireframe (estado inicial)

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ SIGCortinas  /  Agendar visita                                               │
│                                                                             │
│ [1] DATOS DEL CLIENTE                                                       │
│     Cliente:   [________________________________________]                  │
│     Teléfono:  [________________________________________]                  │
│     Dirección: [________________________________________]                  │
│                                                                             │
│ [2] DATOS DE LA VISITA                                                      │
│     Tipo:         [Medición / Instalación / ...__________v]                │
│     Fecha:        [____/____/________]  Hora: [__:__]                       │
│     Técnico:      [{Técnico asignado}____________________v]                │
│     Observaciones:[_______________________________________]                │
│                   [_______________________________________]                │
│                                                                             │
│ [3] DURACIÓN ESTIMADA                                                       │
│     {duración calculada según tipo y ubicación}                             │
│                                                                             │
│ [4] DISPONIBILIDAD                                                          │
│     {si hay cruce: franjas libres de igual duración en próximos 7 días}     │
│     {si no hay franjas: mensaje MSG-12}                                     │
│                                                                             │
│ [5]                         [Confirmar agendamiento]                        │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 2. Tabla de anotaciones

| N.º | Elemento | Comportamiento o regla | Requisito |
|---:|---|---|---|
| 1 | Cliente, teléfono y dirección | Mostrar los datos necesarios para identificar a quién se visitará y dónde. Los campos concretos que son obligatorios deben confirmarse en el detalle de CU-02; no se inventan formatos o longitudes. | Inventario P-04; CU-02. |
| 2 | Tipo de visita | Elegir el tipo de visita de medición o instalación; la duración depende del tipo seleccionado. Las opciones exactas del selector deben ajustarse al catálogo del negocio. | REQ-F-01c; CU-02. |
| 3 | Fecha y hora | Permitir proponer una franja y verificarla contra citas Programadas del mismo Técnico. Los intervalos se manejan como `[inicio, fin)` y la duración debe ser positiva. | REQ-F-01a; Apéndice B del SRS. |
| 4 | Técnico asignado | Identificar el Técnico cuya agenda se comprueba. La vista no debe permitir confirmar una franja ya ocupada. | REQ-F-01a; REQ-NF-02. |
| 5 | Observaciones del trabajo | Registrar notas del trabajo y mostrarlas al Técnico junto con los datos de la cita. | REQ-F-01b. |
| 6 | Duración estimada | Calcular y mostrar la duración; para finca, 4 horas si está a menos de 30 minutos y 8 horas si supera 30 minutos. La frontera exacta de 30 minutos no está resuelta en el SRS. | REQ-F-01c; Apéndice B. |
| 7 | Disponibilidad y alternativas | Si la franja se cruza, rechazarla y mostrar franjas libres de igual duración dentro de los próximos siete días o informar que no hay ninguna. | REQ-F-01a; REQ-NF-07.2. |
| 8 | Acción primaria «Confirmar agendamiento» | Antes de confirmar debe estar comprobada la disponibilidad. Una sola acción primaria, con verbo + objeto. | CU-02; REQ-F-01a. |
| 9 | Aviso por correo M-01 | Al confirmar, guardar la cita en la agenda compartida y generar el correo al Técnico asignado. Si el correo falla, la cita sigue guardada y visible en P-02. | SRS §3.1.4; CU-02, paso 8; inventario M-01. |

## 3. Estados de la pantalla

| Estado | Qué se ve | Qué se conserva de lo digitado | Mensaje (ID) |
|---|---|---|---|
| Inicial | Formulario de cliente, tipo, fecha/hora, Técnico, observaciones y espacio para duración estimada. | Valores vacíos; todavía no hay una visita en proceso. | — |
| Vacío | Si la verificación no encuentra franjas libres de igual duración en los próximos siete días, se muestra el estado sin disponibilidad. No es una pantalla vacía completa. | Conservar los datos de la visita para permitir proponer otra fecha. Esta retención es una decisión propuesta a formalizar. | MSG-12 |
| Cargando | Indicador mientras el sistema calcula duración o consulta la disponibilidad actual del Técnico. | Mantener los datos ya capturados; evitar doble confirmación. | — |
| Con errores de validación | El proyecto no detalla aún todos los campos obligatorios ni sus formatos. Sí se rechaza un cruce; una fecha pasada se rechaza en la reprogramación de P-05. No asignar mensajes para reglas aún no aprobadas. | Mantener valores ya digitados; pendiente fijar qué campos son obligatorios. | MSG-11 para cruce; demás reglas pendientes. |
| Error de servicio | Aviso cuando no puede consultarse disponibilidad o no llega confirmación del agendamiento. No dar por confirmada la cita. | Conservar el formulario como propuesta de interacción; formalizarlo en `PROP-UI-01`. | MSG-15 |
| Éxito | Confirmación de que la cita quedó en la agenda compartida; M-01 se procesa aparte y no debe darse por enviado sin confirmación. | Los datos quedan registrados en la cita. | MSG-14 |
| Sin permiso | Solo la Empleada puede usar P-04 según la matriz de roles. Otros roles reciben denegación en el servidor. | No conservar una operación no autorizada. | MSG-22 |
| Sin conexión | Mostrar que no se recibió confirmación; no duplicar el agendamiento a ciegas. La persona debe consultar la agenda antes de reenviar. | Conservar datos del formulario según la propuesta `PROP-UI-01`; comportamiento pendiente de formalizar. | MSG-23 |

## 4. Pendientes y preguntas abiertas

| ID | Qué falta decidir | Quién lo resuelve | Para cuándo |
|---|---|---|---|
| P04-01 | Completar el flujo de agendamiento REQ-F-12 (alcance futuro) y comprobar si la ficha actual cubre todos los pasos. | Miguel Antonio Gómez Guío (H-05). | Inicio de Unidad 7. |
| P04-02 | Aclarar el cálculo para finca ubicada exactamente a 30 minutos del local. | Gerente / equipo; regla comercial. | Antes de aprobar las reglas de duración. |
| P04-03 | Validar con el Técnico la lectura desde celular, ancho de 360 px y conectividad intermitente. No existe entrevista directa al Técnico. | Juan Miguel Chaparro coordina AM-01. | 28/11/2026 (acción AM-01). |
| P04-04 | Definir la política de reintento/registro de fallo del correo M-01 sin revertir la cita. | Equipo y Gerente. | Antes de cerrar el diseño técnico. |
| P04-05 | Precisar los campos obligatorios, máscaras y formatos de P-04 a partir del CU-02 completo. Esos detalles no están en los archivos del proyecto revisados. | Equipo de requisitos; validar con Empleada y Gerente. | Unidad 7 / antes de implementar. |
| P04-06 | Probar con dos o tres usuarios del perfil real; documentar tareas, hallazgos y cambios. No se encontró evidencia de esa revisión para estas fichas. | Equipo SIGCortinas. | Antes de cerrar la Sesión 3. |

---

## Registro de revisión de las tres fichas

| Elemento | Estado |
|---|---|
| Trazabilidad de cada anotación a requisito, caso de uso o decisión pendiente | Documentada en las tres tablas de anotaciones. |
| Estados de interfaz solicitados por la guía | Incluidos: inicial, vacío, cargando, validación, error de servicio, éxito, sin permiso y sin conexión. Cuando no aplica, se explica. |
| Wireframes en imagen PNG y fuente editable HTML | Pendientes. Esta entrega contiene bocetos textuales editables en Markdown, no imágenes ni prototipos ejecutables. |
| Revisión con dos o tres usuarios reales | Pendiente. No se afirma que se haya realizado. La evidencia de proyecto indica que el Técnico no ha sido entrevistado y que aún faltan validaciones con Gerente y usuarios. |
| Revisión por par del equipo | Pendiente; no se asigna un nombre ni se registra una aprobación no documentada. |

## Fuentes del proyecto usadas

- `17-pantallas/ficha-inventario-pantalla.md` — nombres, propósitos, roles, datos, acciones, estados y navegación de P-02/P-03/P-04.
- `17-pantallas/matriz-trazabilidad-pantallas.md` — relación con CU, requisitos, prioridad y tabla de roles por pantalla.
- `7-srs/srs-sigcortinas.md` — enunciados de REQ-F-01a/01b/01c, REQ-F-02/02a, REQ-F-03, REQ-F-04a/04b, REQ-NF-02 y reglas del Apéndice B.
- `16-usuarios-usabilidad/contexto-uso-tareas.md` — tareas, frecuencia, criticidad, contexto de PER-01 y limitaciones de evidencia.
- `16-usuarios-usabilidad/ficha-persona-usuario.md` — evidencia de PER-01/PER-02 y ausencia de ficha de persona del Técnico.
- `16-usuarios-usabilidad/requisitos-usabilidad-accesibilidad.md` — REQ-NF-07.1/07.2, REQ-NF-08 y REQ-NF-09.
- `10-mejora-adopcion/autoevaluacion-capacidad.md` — acción AM-01 para entrevista y validación con Gerente/Técnico.
- Guía adjunta, secciones 2–4, 6 y actividad de la sección 12 — proceso de wireframe, anotaciones, estados y criterios de revisión.
