# FICHA F-02 · ESC-05 a ESC-08 · CU-02 Agendar visita de medición o instalación

| Campo | Contenido |
|---|---|
| Caso de uso · clase | CU-02 · ESC-05 principal · ESC-06 alterno (3a) · ESC-07 alterno (6a) · ESC-08 excepción (7a) |
| Nivel · diagrama | 1 (caja negra) → DSE-03 · 2 (componentes) → DSE-04 |
| Actores y sistemas | Empleada · Técnico (recibe el aviso) · Sistema SIGCortinas · (N2) Agenda, Registro de clientes, Avisos |
| Elaboró · revisó · fecha | Equipo SIGCortinas · 21/11/2026 |
| Precondición (del CU) | La empleada ha iniciado sesión en el sistema. El cliente acordó con el local (en persona o por teléfono) el tipo de visita (medición o instalación) y una fecha y hora tentativas. El técnico que atenderá la visita tiene usuario activo en el sistema. |
| Resultado esperado (garantía de éxito) | La visita queda registrada en estado «Programada» con cliente, tipo de visita, fecha, hora, dirección, duración estimada y técnico asignado. La cita aparece en la agenda compartida de la gerente, la empleada y el técnico, y el técnico recibe la notificación de la nueva visita. |

## A. Pasos y mensajes (ESC-05 principal)
| Paso del CU | Mensaje (y su retorno) | Quién (de → a) | Requisito | Observaciones |
|---|---|---|---|---|
| 1–2 | **Iniciar agendamiento de visita** (retorno: solicitud de teléfono, tipo de visita y fecha y hora) | Empleada → Sistema | REQ-F-01a, REQ-NF-02 | OS-05. |
| 3–4 | **Enviar datos de la cita** (teléfono, tipo de visita, fecha y hora) (retorno: datos del cliente, duración estimada, técnicos del local) | Empleada → Sistema | REQ-F-01c | OS-06. N2: Agenda → Registro de clientes: *Buscar cliente por teléfono*; auto-mensaje *Calcular duración estimada según el tipo de visita*. |
| 5–6 | **Elegir técnico y registrar observaciones** (retorno: horario disponible, o cruce con franjas libres) | Empleada → Sistema | REQ-F-01a, REQ-F-01b | OS-07. N2: auto-mensaje *Verificar cruce del técnico*. H-01: el CU no describe la respuesta antes del paso 7; se modela como horario disponible para confirmar. |
| 7–8 | **Confirmar agendamiento** (retorno: cita «Programada» en la agenda compartida) | Empleada → Sistema | REQ-F-01a, REQ-F-13, REQ-NF-03 | OS-08. N2: auto-mensaje *Guardar cita*; Agenda → Avisos: *Registrar aviso de nueva visita*; Avisos → Técnico: *Aviso de nueva visita* (asíncrono, D-01). |

## B. Extensiones
| Ext. | Condición | Fragmento · ¿dibujada? | Requisito | Razón si no se dibuja |
|---|---|---|---|---|
| 3a | El teléfono no corresponde a ningún cliente registrado. | `alt` · **Sí** (ESC-06) · OS-10 *Enviar nombre y dirección del cliente* · retoma en 4 | REQ-F-14 | — |
| 4a | La visita es en una finca. | **No** | REQ-F-01c | Regla interna de duración, cubierta por el requisito. Ver P-03. |
| 6a | El técnico ya tiene una cita que se cruza. | `alt` (N1) · `loop` + `opt` (N2) · **Sí** (ESC-07) · retoma en 5 | REQ-F-01a | — |
| 7a | La empleada cancela antes de confirmar. | `break` · **Sí** (ESC-08) · OS-11 *Cancelar agendamiento* · el CU termina sin crear la cita | REQ-NF-03 | — |

## C. Preguntas disparadoras
| Pregunta | Respuesta o estado | Con quién | Produce |
|---|---|---|---|
| ¿Y si el sistema externo no responde? | No aplica: no hay externos (D-01, D-03). El aviso es interno: la cita y su aviso se guardan juntos. | Equipo | Nota en el diagrama. |
| ¿Y si el actor lo envía dos veces? | Una segunda confirmación no crea otra cita: el sistema muestra la ya registrada (D-04). | Equipo | REQ-NF-03. |
| ¿Cuánto debe tardar? ¿Y si se cae a la mitad? | Sin requisito de tiempo definido en las fuentes. REQ-NF-03: sin cita parcial (garantía mínima). | Gerente | Valor no definido en las fuentes. |
| ¿Qué queda registrado y quién lo ve? | Cita en la agenda compartida (tres roles) y aviso para el Técnico, que lo ve en su panel al iniciar sesión (D-01). | Técnico y Gerente | REQ-F-13; observación H-06. |
| ¿Y si el disparo por tiempo no ocurre o se repite? | No hay disparo por tiempo en este escenario. | — | N/A |
