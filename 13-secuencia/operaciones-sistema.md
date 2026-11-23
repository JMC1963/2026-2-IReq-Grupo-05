# Tabla de operaciones del sistema y sus requisitos

| Proyecto · equipo | SIGCortinas · Miguel Antonio Gómez Guío, Edward Steven Rocha Torres, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui |
|---|---|
| Casos de uso y diagramas cubiertos | CU-09 · DSE-01, DSE-02 · CU-02 · DSE-03, DSE-04 |
| Elaboró · revisó | Equipo SIGCortinas |
| Versión · fecha | 1.0 · 21/11/2026 |

## Parte A · Operaciones del sistema (actor → sistema)
| ID | Operación | Entra | Responde | Precondición | CU · paso | Diagrama | Requisitos | Cobertura |
|---|---|---|---|---|---|---|---|---|
| OS-01 | Iniciar registro de garantía | — | Solicitud de pedido y artículo | Gerente con sesión iniciada; garantía tramitada en el portal | CU-09 · 1–2 | DSE-01, DSE-02 | REQ-F-10, REQ-NF-02 | Completa |
| OS-02 | Seleccionar pedido y artículo | Pedido, artículo | Solicitud de motivo, fecha de envío y referencia del caso; o solicitud de datos mínimos (3a) | OS-01 realizada | CU-09 · 3–4, 3a | DSE-01, DSE-02 | REQ-F-10 | Parcial: 3a se cubre con el cambio a REQ-F-10 |
| OS-03 | Enviar datos de la garantía | Motivo, fecha de envío, referencia del caso | Resumen para confirmar; rechazo de fecha (5a); garantía existente con días transcurridos (6a) | Pedido y artículo seleccionados | CU-09 · 5–6, 5a, 6a | DSE-01, DSE-02 | REQ-F-10 | Parcial: 5a y 6a se cubren con el cambio a REQ-F-10 |
| OS-04 | Confirmar registro de garantía | Confirmación | Garantía «En fábrica» con días transcurridos y plazo de espera | Datos válidos y sin garantía abierta | CU-09 · 7–8 | DSE-01, DSE-02 | REQ-F-10, REQ-F-12, REQ-NF-03 | Completa |
| OS-05 | Iniciar agendamiento de visita | — | Solicitud de teléfono, tipo de visita y fecha y hora | Empleada con sesión iniciada; cliente acordó tipo y fecha | CU-02 · 1–2 | DSE-03, DSE-04 | REQ-F-01a, REQ-NF-02 | Completa |
| OS-06 | Enviar datos de la cita | Teléfono, tipo de visita, fecha y hora | Datos del cliente, duración estimada, técnicos del local; o solicitud de nombre y dirección (3a) | OS-05 realizada | CU-02 · 3–4, 3a | DSE-03, DSE-04 | REQ-F-01c, REQ-F-14 | Completa |
| OS-07 | Elegir técnico y registrar observaciones | Técnico, observaciones del trabajo | Horario disponible para confirmar; o cruce con siguientes horarios libres (6a) | Datos de la cita válidos | CU-02 · 5–6, 6a | DSE-03, DSE-04 | REQ-F-01a, REQ-F-01b | Completa |
| OS-08 | Confirmar agendamiento | Confirmación | Cita «Programada» en la agenda compartida | Horario disponible | CU-02 · 7–8 | DSE-03, DSE-04 | REQ-F-01a, REQ-F-13, REQ-NF-03 | Completa |
| OS-09 | Enviar datos mínimos del cliente y del artículo | Datos mínimos del cliente y del artículo | Solicitud de motivo, fecha de envío y referencia del caso | Pedido no registrado (3a) | CU-09 · 3a | DSE-01, DSE-02 | REQ-F-10 | Parcial: cambio a REQ-F-10 |
| OS-10 | Enviar nombre y dirección del cliente | Nombre, dirección | Datos del cliente, duración estimada y técnicos del local | Teléfono sin cliente (3a) | CU-02 · 3a | DSE-03, DSE-04 | REQ-F-14 | Completa |
| OS-11 | Cancelar agendamiento | — | Datos descartados, sin cita creada | Horario disponible, sin confirmar | CU-02 · 7a | DSE-03, DSE-04 | REQ-NF-03 | Completa |

## Parte B · Mensajes salientes e interfaces con sistemas externos (sistema → externo)
Sin filas. El Portal de la fábrica queda fuera del límite del sistema (D-03) y el aviso al Técnico es interno y se muestra en su panel (D-01). Los mensajes entre componentes (Agenda, Registro de clientes, Avisos, Seguimiento de garantías, Registro de pedidos) no cruzan el límite del sistema.

## Parte C · Huecos y preguntas abiertas
| ID | Tipo | Qué falta | Qué se hará | Quién · fecha |
|---|---|---|---|---|
| C-01 | Mensaje sin requisito | «Registrar cliente nuevo» (OS-10) | Se redactó REQ-F-14 | Equipo · 21/11/2026 |
| C-02 | Mensaje sin requisito | «Aviso de nueva visita» (DSE-03, DSE-04) | Se redactó REQ-F-13 | Equipo · 21/11/2026 |
| C-03 | Mensaje sin requisito | Alerta de plazo excedido y plazo en el retorno de OS-04 | Se redactó REQ-F-12 | Equipo · 21/11/2026 |
| C-04 | Mensaje sin requisito | Ramas de cancelación y segunda confirmación (OS-11, D-04) | Se redactó REQ-NF-03 | Equipo · 21/11/2026 |
| C-05 | Requisito parcial | REQ-F-10 no cubre las extensiones 3a, 5a y 6a de CU-09 | Cambio en `requisitos-nuevos/CAMBIO-REQ-F-10.md` | Equipo · 21/11/2026 |
| C-06 | Requisito sin mensaje | REQ-F-02, REQ-F-02a, REQ-F-03, REQ-F-04a, REQ-F-04b, REQ-F-06, REQ-F-11 y REQ-NF-01 | Sus casos de uso (CU-03, CU-04, CU-01, CU-06, CU-08, CU-10) no se dibujaron según la matriz de selección; se cubren con texto y criterios de aceptación | Equipo · 21/11/2026 |
| C-07 | Mensaje sin consumidor | «Aviso de nueva visita»: ningún CU muestra al Técnico leyéndolo (H-06) | Agregar el paso en CU-10 o un caso de uso del panel del Técnico | Equipo · siguiente versión de los CU |
| Q-01 | Pregunta abierta | Tiempo entre la confirmación de una cita y el momento en que el Técnico ve el aviso (P-01) | Se pregunta en el recorrido | Técnico y Gerente · recorrido |
| Q-02 | Pregunta abierta | ¿La alerta de garantía debe aparecer desde el día 10 en lugar del 12? (P-02) | Se pregunta en el recorrido | Gerente · recorrido |
| Q-03 | Pregunta abierta | Cómo se distingue una visita «en finca» (P-03) | Se pregunta en el recorrido | Empleada · recorrido |
