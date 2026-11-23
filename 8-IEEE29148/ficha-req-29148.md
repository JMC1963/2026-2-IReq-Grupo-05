**PLANTILLA DE ESPECIFICACIÓN · UNIDAD 4 · SESIÓN 3 DE 5**

**Ingeniería de Requisitos**

**Fichas de requisitos (ISO/IEC/IEEE 29148) — SIGCortinas**

> **Convención de identificadores:** se emplean los identificadores `REQ-F-xx` y `REQ-NF-xx` establecidos en la traza general del proyecto (`matriz-trazabilidad.md`, casos de uso `CU-01N` a `CU-10` e historias de usuario `HU-01`/`HU-02`).

| **Nombre del proyecto · documento de referencia · fecha** |
|---|
| SIGCortinas · `srs-sigcortinas.md` · 15/11/2026 |

| **Equipo e integrantes** |
|---|
| Miguel Antonio Gómez Guío · Edward Steven Rocha Torres · Juan Miguel Chaparro · Rafael Santiago Barriosnuevo Mongui |

> **Nota sobre el estado de aprobación:** todas las definiciones técnicas y de diseño necesarias para especificar y verificar estos requisitos han sido resueltas por el equipo de desarrollo a partir de las fuentes del proyecto (`acta-constitucion.md`, entrevista a Milena Bermúdez del 28/09/2026, `SIGCortinas-negociacion-WinWin.md`, `matriz-aplicabilidad__.md` y casos de uso `CU-01N` a `CU-10`). Las seis fichas se mantienen en estado **Propuesto** únicamente porque la prueba **Correcto** requiere la aprobación formal de Vicky Beltrán (Gerente), la cual aún no ha sido recabada. De los 13 requisitos especificados en el SRS, se detallan aquí las 6 fichas representativas de la muestra principal; los restantes aparecen trazados en `matriz-trazabilidad.md`.

---

## FICHA 1 · Requisito: REQ-F-01a

| Campo | Contenido |
|---|---|
| **Identificador · tipo** | REQ-F-01a · Funcional |
| **Enunciado** | CUANDO la Empleada solicite agendar una visita, SI el intervalo solicitado se superpone con una cita Programada del mismo Técnico, ENTONCES SIGCortinas deberá rechazar el registro con un mensaje de cruce y mostrar las franjas libres de igual duración dentro de los próximos siete días, o informar que no existen. |
| **Plantilla EARS usada** | Combinada: CUANDO + SI...ENTONCES |
| **Justificación** | Sin esta regla, dos citas del mismo técnico pueden coexistir en la agenda compartida; el técnico llegaría a un sitio sin poder cumplir, y la agenda única dejaría de ser confiable para la Gerente y la Empleada (NI-02). |
| **Fuente** | Entrevista Milena Bermúdez, 28/09/2026, hallazgos 2 y 3; CU-02 (`03-especificacion/casos-de-uso/CU-02.docx`), pasos 5-8 y extensión 6a |
| **Propietario** | Vicky Beltrán (Gerente) — aprobación formal pendiente |
| **Trazabilidad hacia atrás** | NI-02 · G1.1 · HU-02 |
| **Prioridad** | Must (heredada de HU-02/CU-02 en `SIGCortinas-backlog-MoSCoW.md`) |
| **Dependencias y conflictos** | Comparte la regla de disponibilidad del técnico con REQ-F-03 (CU-04): ambas deben verificar cruces mediante un único componente lógico. |
| **Método de verificación** | Prueba · CP-001 |
| **Criterio de aceptación** | Con una cita Programada de 10:00 a 11:00 para un técnico, intentar agendar de 10:30 a 11:30 (debe rechazarse sin guardar registro y ofrecer alternativas sin superposición en los próximos 7 días) y de 11:00 a 12:00 (debe permitirse); 2/2 resultados esperados. |
| **Notas y preguntas abiertas** | Ninguna pendiente a nivel técnico. |
| **Estado · responsable** | Propuesto (verificado documentalmente; pendiente firma de la Gerente) · Miguel Gómez |
| **Nueve pruebas** | Necesario ✓ · Apropiado ✓ · No ambiguo ✓ · Completo ✓ · Singular ✓ · Factible ✓ · Verificable ✓ · Correcto **?** (pendiente aprobación de Vicky Beltrán) · Conforme ✓ |

---

## FICHA 2 · Requisito: REQ-F-02

| Campo | Contenido |
|---|---|
| **Identificador · tipo** | REQ-F-02 · Funcional |
| **Enunciado** | CUANDO la Gerente o el Técnico accedan al panel principal, SIGCortinas deberá mostrar las actividades programadas para la fecha actual, ordenadas por hora, con cliente, tipo de visita, dirección, técnico y estado, y deberá reflejar cualquier cita creada, reprogramada o cancelada la próxima vez que el usuario abra o recargue el panel; SI no existen actividades para esa fecha, ENTONCES deberá informarlo y mostrar la fecha de la próxima cita programada. |
| **Plantilla EARS usada** | Combinada: CUANDO + SI...ENTONCES |
| **Justificación** | Sin un panel diario confiable, la Gerente y el Técnico vuelven a depender del cuaderno o de consultas verbales para conocer la programación del día (NI-02). |
| **Fuente** | Entrevista Milena Bermúdez, hallazgo 2; `acta-constitucion.md`, Criterios de éxito; CU-03, pasos 1-2 y extensión 2a; HU-01 |
| **Propietario** | Vicky Beltrán (Gerente) — aprobación formal pendiente |
| **Trazabilidad hacia atrás** | NI-02 (s) · G1.1 · HU-01 |
| **Prioridad** | Must (heredada de HU-01/CU-03 en `SIGCortinas-backlog-MoSCoW.md`) |
| **Dependencias y conflictos** | Debe reflejar los cambios ejecutados por REQ-F-03 sobre las citas (reprogramación o cancelación) disparándose desde el mismo evento de actualización. |
| **Método de verificación** | Prueba · CP-002 |
| **Criterio de aceptación** | Crear citas con fechas distintas; iniciar sesión en la fecha actual y comprobar que solo aparecen las del día ordenadas por hora; probar una fecha sin citas y comprobar el mensaje y la próxima cita; crear o modificar una cita y comprobar que se refleja al abrir o recargar el panel. 3/3 resultados esperados. |
| **Notas y preguntas abiertas** | Confirmar con la Gerente si el refresco al abrir/recargar satisface la operación diaria o si requiere actualización automática en vivo. |
| **Estado · responsable** | Propuesto (verificado documentalmente; pendiente firma de la Gerente) · Edward Rocha |
| **Nueve pruebas** | Necesario ✓ · Apropiado ✓ · No ambiguo ✓ · Completo ✓ · Singular ✓ · Factible ✓ · Verificable ✓ · Correcto **?** (pendiente aprobación de Vicky Beltrán) · Conforme ✓ |

---

## FICHA 3 · Requisito: REQ-F-03

| Campo | Contenido |
|---|---|
| **Identificador · tipo** | REQ-F-03 · Funcional |
| **Enunciado** | CUANDO la Empleada confirme la reprogramación o cancelación de una cita, SIGCortinas deberá actualizar la cita en la agenda compartida con la nueva fecha y hora, o con el estado «Cancelada», registrar el motivo del cambio y notificar al Técnico y a la Gerente; SI la nueva fecha y hora son anteriores al momento actual o se cruzan con otra cita del mismo Técnico, ENTONCES deberá rechazar el cambio e indicar la causa. |
| **Plantilla EARS usada** | Combinada: CUANDO + SI...ENTONCES |
| **Justificación** | Responde a la principal dificultad operativa reportada por la Empleada (NI-03): evitar agendas paralelas y falta de aviso ante cambios solicitados por el cliente. |
| **Fuente** | Entrevista Milena Bermúdez, hallazgo 3; `SIGCortinas-negociacion-WinWin.md` (acuerdo candidato, opción 3); CU-04, pasos 4-8 y extensiones 5a, 5b, 6a |
| **Propietario** | Vicky Beltrán (Gerente) — aprobación formal pendiente |
| **Trazabilidad hacia atrás** | NI-03 · G1.2 |
| **Prioridad** | Must (`SIGCortinas-backlog-MoSCoW.md`, fila CU-04) |
| **Dependencias y conflictos** | Comparte la regla de disponibilidad del técnico con REQ-F-01a mediante un único componente de verificación de cruces. El canal de notificación definido es correo electrónico inmediato (SRS §3.1.4). |
| **Método de verificación** | Prueba · CP-003 |
| **Criterio de aceptación** | Reprogramar una cita a una fecha pasada (rechazo); a un horario cruzado con otra cita del mismo técnico (rechazo indicando causa); a un horario libre (éxito, con registro de motivo y envío de notificación por correo); cancelar una cita y comprobar liberación de la franja. 4/4 resultados esperados. |
| **Notas y preguntas abiertas** | Ratificación formal del acuerdo WinWin por las partes involucradas. |
| **Estado · responsable** | Propuesto (verificado documentalmente; pendiente firma de la Gerente) · Miguel Gómez |
| **Nueve pruebas** | Necesario ✓ · Apropiado ✓ · No ambiguo ✓ · Completo ✓ · Singular ✓ · Factible ✓ · Verificable ✓ · Correcto **?** (pendiente aprobación de Vicky Beltrán) · Conforme ✓ |

---

## FICHA 4 · Requisito: REQ-F-04b

| Campo | Contenido |
|---|---|
| **Identificador · tipo** | REQ-F-04b · Funcional |
| **Enunciado** | SI la Empleada intenta guardar un pedido con un abono inicial distinto del 50 % del total acordado (redondeado al peso superior), ENTONCES SIGCortinas deberá rechazar la operación completa, sin crear pedido ni pago, e informar el importe requerido. |
| **Plantilla EARS usada** | SI...ENTONCES |
| **Justificación** | Garantiza la coherencia financiera entre el anticipo inicial y el cálculo posterior del saldo pendiente en CU-05, conforme a la práctica comercial del negocio (NI-06). |
| **Fuente** | Entrevista Milena Bermúdez, hallazgo 6; CU-01N, paso 5, extensión 6b y garantía mínima |
| **Propietario** | Vicky Beltrán (Gerente) — aprobación formal pendiente |
| **Trazabilidad hacia atrás** | NI-06 · G2.1 |
| **Prioridad** | Must (heredada de CU-01N en `SIGCortinas-backlog-MoSCoW.md`) |
| **Dependencias y conflictos** | Relacionado directamente con CU-05 (registro de pago del saldo); cualquier ajuste en el porcentaje exigido implica actualizar el cálculo en CU-05. |
| **Método de verificación** | Prueba · CP-004 |
| **Criterio de aceptación** | Para un pedido con total de $100.000, intentar guardar con abonos de −$1, $49.999, $100.001 y $50.000; los tres primeros deben rechazarse sin crear pedido ni registro de pago, y el cuarto debe aceptarse. 4/4 resultados esperados. |
| **Notas y preguntas abiertas** | Confirmar con la Gerente si la regla comercial es estrictamente el 50 % exacto o si admite abonos superiores en casos particulares (decisión D-02). |
| **Estado · responsable** | Propuesto (verificado documentalmente; pendiente firma de la Gerente) · Miguel Gómez |
| **Nueve pruebas** | Necesario ✓ · Apropiado ✓ · No ambiguo ✓ · Completo ✓ · Singular ✓ · Factible ✓ · Verificable ✓ · Correcto **?** (regla del 50 % pendiente de confirmación de Vicky Beltrán) · Conforme ✓ |

---

## FICHA 5 · Requisito: REQ-F-06

| Campo | Contenido |
|---|---|
| **Identificador · tipo** | REQ-F-06 · Funcional |
| **Enunciado** | CUANDO la Empleada ingrese un criterio de búsqueda de inventario, SIGCortinas deberá mostrar los artículos coincidentes con su existencia disponible (en rollos, metros o unidades) y la fecha de la última actualización; SI ningún artículo coincide con el criterio, ENTONCES deberá informarlo; SI la existencia de un artículo coincidente es cero, ENTONCES deberá marcarlo como «Agotado». |
| **Plantilla EARS usada** | Combinada: CUANDO + dos SI...ENTONCES |
| **Justificación** | Elimina la consulta manual o estimada sobre disponibilidad de materiales al atender clientes en el local (NI-08). |
| **Fuente** | Guía de entrevista, sección 10; CU-06, pasos 4 y 6, extensiones 4a y 4b |
| **Propietario** | Vicky Beltrán (Gerente) — aprobación formal pendiente |
| **Trazabilidad hacia atrás** | NI-08 · G2.2 |
| **Prioridad** | Must (`SIGCortinas-backlog-MoSCoW.md`, fila CU-06) |
| **Dependencias y conflictos** | Depende de los datos actualizados mediante CU-07 (REQ-F-08, gestión de entradas/salidas de inventario) en cuanto a unidades de medida y fecha de actualización. |
| **Método de verificación** | Prueba · CP-005 |
| **Criterio de aceptación** | Buscar un artículo con existencia positiva, un artículo con existencia cero y un término sin coincidencias; verificar que se muestre el detalle con unidad y fecha en el primero, la etiqueta «Agotado» en el segundo y el mensaje de «sin resultados» en el tercero. 3/3 resultados esperados. |
| **Notas y preguntas abiertas** | Ninguna pendiente a nivel técnico. |
| **Estado · responsable** | Propuesto (verificado documentalmente; pendiente firma de la Gerente) · Juan Chaparro |
| **Nueve pruebas** | Necesario ✓ · Apropiado ✓ · No ambiguo ✓ · Completo ✓ · Singular ✓ · Factible ✓ · Verificable ✓ · Correcto **?** (pendiente aprobación de Vicky Beltrán) · Conforme ✓ |

---

## FICHA 6 · Requisito: REQ-NF-02

| Campo | Contenido |
|---|---|
| **Identificador · tipo** | REQ-NF-02 · No funcional (seguridad y control de acceso) |
| **Enunciado** | SIGCortinas deberá restringir el acceso a los datos personales de clientes y a las funciones de registro, modificación y consulta según el rol del usuario (Gerente, Empleada, Técnico), de manera que cada rol solo pueda ejecutar las acciones autorizadas explícitamente en los casos de uso del sistema; SI una acción o consulta no está autorizada para un rol, ENTONCES SIGCortinas deberá negarla por defecto. |
| **Plantilla EARS usada** | Ubicua + SI...ENTONCES |
| **Justificación** | Cumplimiento obligatorio de la Ley 1581 de 2012 sobre protección de datos personales (NI-11), dado que el sistema almacena nombres, teléfonos, direcciones e historial comercial de los clientes. |
| **Fuente** | `matriz-aplicabilidad__.md`, fila 13 (Ley 1581 de 2012, «Aplica»); casos de uso `CU-01N` a `CU-10` |
| **Propietario** | Vicky Beltrán (Gerente) — aprobación formal pendiente |
| **Trazabilidad hacia atrás** | NI-11 · — (requisito transversal de origen legal) |
| **Prioridad** | Must (`SIGCortinas-backlog-MoSCoW.md`, fila propia por exigencia legal) |
| **Dependencias y conflictos** | Debe equilibrarse con la facilidad de uso requerida por la Empleada (entrevista, hallazgo 9) para no introducir fricción innecesaria en la captura rápida de pedidos y citas. |
| **Método de verificación** | Prueba · CP-006 (acciones autorizadas por rol) + Inspección · IN-001 (denegación por defecto de acciones no autorizadas) |
| **Criterio de aceptación** | Para cada caso de uso (`CU-01N` a `CU-10`), ejecutar la operación con el rol autorizado (debe permitirse) y con los dos roles restantes (debe rechazarse); 100 % de conformidad. Verificar por inspección que cualquier función administrativa o fuera del alcance asignado al rol quede bloqueada por defecto. |
| **Notas y preguntas abiertas** | Ratificación por parte de la Gerente de los alcances operativos asignados a cada rol en los casos de uso. |
| **Estado · responsable** | Propuesto (verificado documentalmente; pendiente firma de la Gerente) · Rafael Barriosnuevo |
| **Nueve pruebas** | Necesario ✓ · Apropiado ✓ · No ambiguo ✓ · Completo ✓ · Singular ✓ · Factible ✓ · Verificable ✓ · Correcto **?** (pendiente aprobación de Vicky Beltrán) · Conforme ✓ |

---

*Cada ficha se almacena de forma individual en `08-requisitos-29148/fichas/`.*
