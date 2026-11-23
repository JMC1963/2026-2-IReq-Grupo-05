**Especificación de Requisitos de Software (SRS) — SIGCortinas**

**Estructura adaptada de IEEE 830-1998**

> **Alcance de esta especificación:** este documento recoge los **13 requisitos** funcionales y no funcionales especificados para el núcleo operativo de **SIGCortinas**, fundamentados en el acta de constitución, la entrevista con Milena Bermúdez (28/09/2026), el acuerdo de negociación WinWin, la matriz de aplicabilidad legal y los casos de uso `CU-01N` a `CU-10`. Las decisiones técnicas y de diseño han sido establecidas por el equipo de desarrollo a partir de dichas fuentes; la aprobación formal de línea base queda sujeta a la revisión y firma de la Gerente (Vicky Beltrán).

---

## Portada

| Campo | Contenido |
|---|---|
| **Nombre del producto (y nombre corto)** | SIGCortinas — Sistema de gestión para el negocio de cortinas y persianas (Tunja, Boyacá). Nombre corto: SIGCortinas. |
| **Organización / cliente** | Cortinas Ambiente Moderno — local principal, Barrio Santa Inés, Tunja. Patrocinadora: Vicky Beltrán (Gerente). |
| **Estado y fecha** | Propuesto (pendiente de aprobación formal de la Gerente) — 15/11/2026. |
| **Autor(es) y revisores** | Autores: Miguel Antonio Gómez Guío, Edward Steven Rocha Torres, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui. Revisor cruzado: por asignar — pendiente. |
| **Aprobación del alcance** | Vicky Beltrán — Gerente y patrocinadora. Pendiente de firma. |

---

## 1. Introducción

### 1.1 Propósito

Este documento especifica los requisitos de software de **SIGCortinas** para **Cortinas Ambiente Moderno** (Tunja, Boyacá). Está dirigido a la Gerente y patrocinadora (Vicky Beltrán), a la Empleada y al Técnico como usuarios operativos, al equipo de desarrollo y al docente evaluador del curso de Ingeniería de Requisitos de la UPTC. Detalla 13 requisitos prioritarios dentro del conjunto total estimado de 18 requisitos que cubren completamente los casos de uso `CU-01N` a `CU-10` y las historias de usuario `HU-01` y `HU-02` (ver «Requisitos de alcance futuro», al final de la sección 3).

### 1.2 Alcance

- **Producto:** aplicación web de gestión operativa para agenda de visitas técnicas, registro de pedidos y abonos, consulta de inventario y seguimiento de garantías.
- **Criterios de éxito (`acta-constitucion.md`):** permitir a la Gerente localizar cualquier venta pasada o existencia de inventario en menos de 1 minuto, eliminar cruces de horario en la agenda del Técnico y controlar el cumplimiento de plazos de garantía con fábrica.
- **Exclusiones explícitas:** integración directa con sistemas externos de fábrica, facturación electrónica ante la DIAN, portal de acceso para clientes o proveedores, aplicación móvil nativa y gestión multi-sede.

### 1.3 Definiciones, acrónimos y abreviaturas

| Término | Definición operativa |
|---|---|
| Cita Programada | Visita de medición o instalación registrada con cliente, fecha, hora, dirección y técnico asignado, en estado «Programada» (CU-02). |
| Cruce de horario | Superposición temporal entre dos citas del mismo técnico bajo intervalos semiabiertos `[inicio, fin)`. |
| Abono inicial | Pago parcial registrado al crear un pedido; corresponde al 50 % del total acordado, redondeado al peso superior si existe fracción. **Pendiente de ratificación comercial por la Gerente (D-02)**. |
| Duración de visita en finca | Estimación operativa definida por el equipo: **4 horas** si la finca se ubica a menos de 30 minutos del local y **8 horas** si se ubica a más de 30 minutos; la Empleada selecciona la duración según la dirección registrada al agendar (CU-02). Pendiente de confirmación por la Gerente. |
| Condiciones normales de operación | Operación estándar con conexión a Internet estable y volumen de transacciones correspondiente al piloto operativo (27/11/2026 al 11/12/2026), sin degradación externa de red. |
| Saldo pendiente | Diferencia entre el valor total acordado de un pedido y la suma de los abonos registrados (CU-05). |
| Garantía «En fábrica» / Plazo excedido | Artículo devuelto a fábrica por defecto de fabricación con plazo estándar de 10 a 12 días calendario desde su envío; pasa a estado «Plazo excedido» al superar los 12 días (CU-09; meta G3.2). |
| Existencia | Cantidad física disponible de un artículo en inventario, expresada en rollos, metros o unidades (CU-06, CU-07). |
| Pedido «Pendiente» / «Pagado» | Estados financieros del pedido según exista o no saldo pendiente de cobro (CU-01N, CU-05). |

### 1.4 Referencias

| ID | Documento |
|---|---|
| REF-01 | `acta-constitucion.md` — Acta de constitución del proyecto SIGCortinas |
| REF-02 | Entrevista a Milena Bermúdez (Empleada), 28/09/2026 |
| REF-03 | `SIGCortinas-negociacion-WinWin.md` — Acuerdos de negociación con interesados |
| REF-04 | `matriz-aplicabilidad__.md` — Matriz de aplicabilidad legal y normativa |
| REF-05 | Casos de uso `CU-01N` a `CU-10` e historias de usuario `HU-01`, `HU-02` |
| REF-06 | `strs-sigcortinas.md` — Especificación de necesidades de los interesados (`NI-01` a `NI-11`) |
| REF-07 | `matriz-trazabilidad.md` — Matriz de trazabilidad completa del proyecto |
| REF-08 | `SIGCortinas-backlog-MoSCoW.md` — Backlog priorizado y estimación de esfuerzo |

### 1.5 Visión general

El documento se organiza en tres secciones: la sección 1 establece el propósito, alcance, glosario y referencias; la sección 2 describe el entorno operativo, los perfiles de usuario y las restricciones generales; y la sección 3 especifica los requisitos de interfaces externas, los requisitos funcionales y no funcionales detallados bajo sintaxis EARS y las reglas de diseño del sistema.

---

## 2. Descripción general

### 2.1 Perspectiva del producto y dispositivos de acceso

SIGCortinas reemplaza el control manual basado en cuadernos y hojas de cálculo aisladas en el local principal de Cortinas Ambiente Moderno:
- **Gerente y Empleada:** operan el sistema desde el computador de escritorio o portátil existente en el local mediante navegador web.
- **Técnico:** accede desde el navegador web de su teléfono móvil a través de una interfaz adaptable (*responsive*), sin requerir instalación de aplicación móvil nativa.

### 2.2 Funciones del producto

1. Gestión de agenda compartida: agendamiento sin cruces de horario, visualización diaria en panel principal, reprogramación y cancelación con registro de motivo.
2. Gestión comercial de pedidos: validación de datos obligatorios, control de abono inicial y cálculo de saldos.
3. Control de inventario y garantías: consulta de existencias en tiempo real y monitoreo de plazos de garantías enviadas a fábrica.
4. Seguridad y trazabilidad: control de acceso basado en roles y conservación de registros de venta y garantía.

### 2.3 Características de los usuarios

- **Gerente (Vicky Beltrán):** supervisión general, consulta de ventas e inventario, control de garantías y seguimiento diario de operaciones.
- **Empleada (Milena Bermúdez):** atención en punto de venta, agendamiento y reprogramación de visitas, registro de pedidos y consulta rápida de existencias. Requiere flujos ágiles de captura de datos.
- **Técnico:** consulta de agenda diaria en campo, visualización de observaciones técnicas de cada visita y reporte de ejecución.

### 2.4 Restricciones generales

- **Protección de datos personales:** cumplimiento de la Ley 1581 de 2012 para el tratamiento de datos de clientes (`matriz-aplicabilidad__.md`, fila 13), originando el requisito **REQ-NF-02**.
- **Garantía legal y conservación de evidencia:** cumplimiento de la Ley 1480 de 2011 respecto a la conservación de evidencia de venta y garantía durante el término legal de reclamación (`matriz-aplicabilidad__.md`, fila 14), originando el requisito **REQ-NF-03**.

### 2.5 Suposiciones y dependencias

- El local cuenta con conexión a Internet activa durante el horario de atención y el Técnico dispone de datos móviles para consultar su agenda.
- Los valores de reglas de negocio sujetos a ratificación comercial (porcentaje exacto de abono inicial y confirmación de distancias a fincas) se implementan de forma parametrizable.

---

## 3. Requisitos específicos

### 3.1 Interfaces externas

- **3.1.1 Interfaces de usuario:** interfaz web de escritorio optimizada para captura rápida en el local (Gerente y Empleada) e interfaz web *responsive* para consulta móvil en campo (Técnico).
- **3.1.2 Interfaces de hardware:** no aplica integración con periféricos especializados en esta fase.
- **3.1.3 Interfaces de software:** sistema autónomo sin integración directa con software de proveedores o fábrica.
- **3.1.4 Interfaces de comunicaciones:** las notificaciones automáticas al Técnico y a la Gerente ante agendamientos, reprogramaciones o cancelaciones de citas (`CU-02` paso 8, `CU-04` paso 8) se envían de forma inmediata mediante **correo electrónico**.

### 3.2 a 3.6 · Requisitos funcionales y no funcionales

| Requisito 1 · REQ-F-01a | Agendar visita sin cruce de horario | Must |
|---|---|---|
| CUANDO la Empleada solicite agendar una visita, SI el intervalo solicitado se superpone con una cita Programada del mismo Técnico, ENTONCES SIGCortinas deberá rechazar el registro con un mensaje de cruce y mostrar las franjas libres de igual duración dentro de los próximos siete días, o informar que no existen. | Origen: `CU-02`, pasos 5-8, ext. 6a; `HU-02` | Verificación: con cita 10:00-11:00, probar 10:30-11:30 (rechazo + alternativas) y 11:00-12:00 (permitido); 2/2. |

| Requisito 2 · REQ-F-02 | Mostrar actividades del día en el panel | Must |
|---|---|---|
| CUANDO la Gerente o el Técnico accedan al panel principal, SIGCortinas deberá mostrar las actividades programadas para la fecha actual, ordenadas por hora, con cliente, tipo de visita, dirección, técnico y estado, y deberá reflejar cualquier cita creada, reprogramada o cancelada la próxima vez que el usuario abra o recargue el panel; SI no existen actividades para esa fecha, ENTONCES deberá informarlo y mostrar la fecha de la próxima cita programada. | Origen: `CU-03`, pasos 1-2, ext. 2a; `HU-01` | Verificación: igual a FICHA 2 de `ficha-req-29148.md`; 3/3. |

| Requisito 3 · REQ-F-03 | Reprogramar o cancelar cita | Must |
|---|---|---|
| CUANDO la Empleada confirme la reprogramación o cancelación de una cita, SIGCortinas deberá actualizar la cita en la agenda compartida, registrar el motivo y notificar al Técnico y a la Gerente; SI la nueva fecha es anterior al momento actual o se cruza con otra cita del mismo Técnico, ENTONCES deberá rechazar el cambio e indicar la causa. | Origen: `CU-04`, pasos 4-8, ext. 5a/5b/6a | Verificación: 4/4 (fecha pasada, cruce, horario libre, cancelación). |

| Requisito 4 · REQ-F-04a | Rechazar pedido con campos faltantes | Must |
|---|---|---|
| SI la Empleada intenta guardar un pedido sin alguno de los campos obligatorios definidos en la regla de diseño (Apéndice B), ENTONCES SIGCortinas deberá rechazar el registro e identificar cada campo faltante. | Origen: `CU-01N`, ext. 6a | Verificación: omitir cada campo por separado; 100 % de rechazos. |

| Requisito 5 · REQ-F-04b | Rechazar abono inicial inválido | Must |
|---|---|---|
| SI la Empleada intenta guardar un pedido con un abono inicial distinto del 50 % del total (redondeado al peso superior), ENTONCES SIGCortinas deberá rechazar la operación completa, sin crear pedido ni pago, e informar el importe requerido. | Origen: `CU-01N`, ext. 6b | Verificación: $100.000 con abonos −$1, $49.999, $100.001, $50.000; 4/4. |

| Requisito 6 · REQ-F-06 | Consultar existencia de un artículo | Must |
|---|---|---|
| CUANDO la Empleada ingrese un criterio de búsqueda, SIGCortinas deberá mostrar los artículos coincidentes con su existencia y fecha de actualización; SI ningún artículo coincide, informarlo; SI la existencia es cero, marcarlo «Agotado». | Origen: `CU-06`, pasos 4 y 6, ext. 4a/4b | Verificación: 3/3. |

| Requisito 7 · REQ-NF-01 | Tiempo de respuesta de búsqueda < 60 s | Must |
|---|---|---|
| SIGCortinas deberá devolver los resultados de una búsqueda de historial o de inventario en menos de 60 segundos, en el 100 % de las consultas del piloto, bajo condiciones normales de operación (definidas en §1.3). | Origen: `acta-constitucion.md`, Criterios de éxito; `CU-08` | Verificación: medir N búsquedas reales del piloto; 100 % < 60 s. |

| Requisito 8 · REQ-NF-02 | Control de acceso por rol | Must |
|---|---|---|
| SIGCortinas deberá restringir el acceso a los datos personales y funciones según el rol (Gerente, Empleada, Técnico) conforme a las acciones asignadas a cada uno en los casos de uso del sistema; SI una acción o consulta no está autorizada para un rol, ENTONCES deberá negarla por defecto. | Origen: Ley 1581 de 2012; casos de uso `CU-01N` a `CU-10` | Verificación: ver FICHA 6 de `ficha-req-29148.md` (CP-006 e IN-001). |

| Requisito 9 · REQ-F-01b | Observaciones del trabajo al agendar | Must |
|---|---|---|
| CUANDO la Empleada seleccione el Técnico al agendar una visita, SIGCortinas deberá permitir registrar observaciones del trabajo y mostrarlas al Técnico junto con los demás datos de la cita. | Origen: `NI-04` · `CU-02`, paso 5 | Verificación: 1/1. |

| Requisito 10 · REQ-F-01c | Duración estimada de la visita | Must |
|---|---|---|
| CUANDO la Empleada registre el tipo de visita, SIGCortinas deberá calcular y mostrar la duración estimada y bloquear esa franja en la agenda del Técnico; SI la visita es en finca, ENTONCES la duración deberá ser de 4 u 8 horas según la regla de §1.3. | Origen: `NI-07` · `CU-02`, paso 4, ext. 4a | Verificación: 3/3 (urbana, finca 4 h, finca 8 h). |

| Requisito 11 · REQ-F-02a | Señalar citas sin confirmación previa | Must |
|---|---|---|
| CUANDO existan citas del día cuya confirmación previa al cliente no esté registrada, SIGCortinas deberá resaltarlas como «Por confirmar» en el listado de actividades del día. | Origen: `NI-05` · `CU-03`, ext. 2b | Verificación: 1/1. |

| Requisito 12 · REQ-F-10 | Registrar garantía y calcular plazo | Must |
|---|---|---|
| CUANDO la Gerente registre una garantía enviada a la fábrica, SIGCortinas deberá guardarla en estado «En fábrica», calcular los días transcurridos, y SI superan 12 días, ENTONCES marcarla «Plazo excedido» y mostrar alerta en el panel (REQ-F-02). | Origen: `NI-10` · `CU-09`, pasos 4-8; `CU-03`, ext. 2c | Verificación: 2/2 (sin alerta, con alerta a 13 días). |

| Requisito 13 · REQ-F-11 | Registrar resultado de visita y validar satisfacción | **Could** |
|---|---|---|
| CUANDO el Técnico registre el resultado de una visita, SIGCortinas deberá marcar la cita «Realizada», guardar los datos y avisar a la Empleada para validar satisfacción; SI el cliente no estaba, ENTONCES marcar «No realizada» y notificar sin modificar el pedido. | Origen: `NI-05` · `CU-10`, pasos 4-8, ext. 3a | Verificación: 2/2. |

| Requisito 14 · REQ-NF-03 | Conservación de datos de venta y garantía | Must (exigencia legal) |
|---|---|---|
| SIGCortinas deberá conservar, para cada pedido, la fecha de compra, el producto o servicio vendido y el estado de la garantía, durante al menos el tiempo que la Ley 1480 de 2011 exige para reclamaciones de garantía legal. | Origen: Ley 1480 de 2011; `matriz-aplicabilidad__.md`, fila 14 | Verificación: crear un pedido con garantía y comprobar que sus datos permanecen íntegros y disponibles. **Pendiente**: confirmación del plazo legal exacto en días/meses por asesoría legal o contable. |

### Apéndice B. Reglas de diseño y restricciones técnicas

- **Intervalos de cita:** representados como intervalos semiabiertos `[inicio, fin)` con duración estrictamente positiva.
- **Duración en finca:** 4 horas si la ubicación se encuentra a menos de 30 minutos del local; 8 horas si supera los 30 minutos.
- **Campos obligatorios del pedido:** nombre del cliente, teléfono, tipo de producto/servicio, valor total positivo, abono inicial y medidas/especificaciones técnicas.
- **Abono inicial:** 50 % del valor total acordado, redondeado al peso superior (pendiente de ratificación comercial por la Gerente, D-02).
- **Comprobante de pago:** documento digital generado en pantalla, descargable y enviable por correo electrónico al cliente, sin dependencia de impresora térmica dedicada.
- **Migración inicial de datos:** carga única mediante plantilla estructurada (CSV/Excel) con clientes activos, pedidos abiertos y existencias vigentes al inicio del piloto.
- **Control de acceso por rol:** cada rol (Gerente, Empleada, Técnico) accede exclusivamente a las operaciones asignadas en sus respectivos casos de uso (`CU-01N` a `CU-10`); toda acción no autorizada explícitamente se deniega por defecto.
- **Sincronización de agenda:** la notificación por correo electrónico de REQ-F-03 y la actualización de datos consultada por el panel de REQ-F-02 se ejecutan a partir del mismo evento transaccional de modificación de cita.
- **Componente único de verificación de cruce:** REQ-F-01a y REQ-F-03 invocan un único componente compartido de validación de disponibilidad del Técnico.

### Requisitos de alcance futuro (Unidad 7)

| ID | Caso de uso de origen |
|---|---|
| REQ-F-05 | `CU-01N` (flujo completo de creación de pedido) |
| REQ-F-07 | `CU-05` (registro de pago de saldo y cierre financiero) |
| REQ-F-08 | `CU-07` (actualización de entradas y salidas de inventario) |
| REQ-F-09 | `CU-08` (consulta histórica detallada de ventas) |
| REQ-F-12 | `CU-02` (flujo completo de agendamiento) |

*Se almacena en `07-srs-830/srs-sigcortinas.md`.*
