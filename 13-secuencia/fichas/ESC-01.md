# FICHA F-01 · ESC-01 a ESC-04 · CU-09 Registrar una garantía enviada a la fábrica

| Campo | Contenido |
|---|---|
| Caso de uso · clase | CU-09 · ESC-01 principal · ESC-02 alterno (3a) · ESC-03 alterno (5a) · ESC-04 excepción (6a) |
| Nivel · diagrama | 1 (caja negra) → DSE-01 · 2 (componentes) → DSE-02 |
| Actores y sistemas | Gerente · Sistema SIGCortinas · (N2) Seguimiento de garantías, Registro de pedidos |
| Elaboró · revisó · fecha | Equipo SIGCortinas · 21/11/2026 |
| Precondición (del CU) | La gerente ha iniciado sesión en el sistema. El cliente reportó un problema con un artículo comprado y la gerente decidió enviarlo a la fábrica por garantía. La garantía se tramita en el portal de la fábrica, fuera del sistema. |
| Resultado esperado (garantía de éxito) | La garantía queda registrada en estado «En fábrica» con el pedido y el artículo de origen, el motivo, la fecha de envío y la referencia del caso en el portal. El sistema calcula los días transcurridos y programa la alerta para cuando se supere el plazo de espera (10 a 12 días). |

## A. Pasos y mensajes (ESC-01 principal)
| Paso del CU | Mensaje (y su retorno) | Quién (de → a) | Requisito | Observaciones |
|---|---|---|---|---|
| 1–2 | **Iniciar registro de garantía** (retorno: solicitud de pedido y artículo) | Gerente → Sistema | REQ-F-10, REQ-NF-02 | OS-01. |
| 3–4 | **Seleccionar pedido y artículo** (retorno: solicitud de motivo, fecha de envío y referencia del caso) | Gerente → Sistema | REQ-F-10 | OS-02. N2: Seguimiento de garantías → Registro de pedidos: *Buscar pedido y artículo* (retorno: datos o pedido no registrado). |
| 5 | **Enviar datos de la garantía** (motivo, fecha de envío, referencia del caso) (retorno: resumen para confirmar) | Gerente → Sistema | REQ-F-10 | OS-03. H-01: el CU no describe la respuesta del sistema en este punto; se modela como resumen para confirmar. |
| 6 | *Sin mensaje propio: paso interno de validación.* | — | REQ-F-10, REQ-NF-03 | N2: Seguimiento de garantías → Registro de pedidos: *Verificar que el artículo pertenece al pedido*; auto-mensaje *Buscar garantía abierta del artículo*. |
| 7–8 | **Confirmar registro de garantía** (retorno: garantía «En fábrica», días transcurridos y plazo de espera) | Gerente → Sistema | REQ-F-10, REQ-F-12, REQ-NF-03 | OS-04. N2: auto-mensaje *Crear garantía «En fábrica» y calcular días transcurridos*. |

## B. Extensiones
| Ext. | Condición | Fragmento · ¿dibujada? | Requisito | Razón si no se dibuja |
|---|---|---|---|---|
| 3a | El pedido no está registrado (compra anterior a SIGCortinas). | `alt` · **Sí** (ESC-02) · mensaje OS-09 *Enviar datos mínimos del cliente y del artículo* · retoma en 4 | REQ-F-10 (ampliado, ver `CAMBIO-REQ-F-10.md`) | — |
| 5a | La fecha de envío es posterior a la fecha actual. | `alt` · **Sí** (ESC-03) · retoma en 5 | REQ-F-10 (ampliado) | — |
| 6a | El artículo ya tiene una garantía abierta. | `break` · **Sí** (ESC-04) · el CU termina sin crear | REQ-F-10 (ampliado), REQ-NF-03 | — |
| H-02 | Cancelar antes de confirmar | No existe en el CU | REQ-NF-03 | Se dibuja cuando el CU incluya la extensión. |
| H-03 | Falla al guardar | No existe en el CU | REQ-NF-03 | Se trata en el recorrido. |

## C. Preguntas disparadoras
| Pregunta | Respuesta o estado | Con quién | Produce |
|---|---|---|---|
| ¿Y si el sistema externo no responde? | No aplica: el portal de la fábrica no tiene integración (D-03). | Equipo | Nota en el diagrama. |
| ¿Y si el actor lo envía dos veces? | La regla 6a evita una segunda garantía abierta del mismo artículo; una segunda confirmación muestra la garantía existente (D-04). | Equipo | REQ-NF-03. |
| ¿Cuánto debe tardar? ¿Y si se cae a la mitad? | Sin requisito de tiempo definido en las fuentes. REQ-NF-03: no quedan registros parciales. | Gerente | Valor no definido en las fuentes. |
| ¿Qué queda registrado y quién lo ve? | Garantía «En fábrica» visible a Gerente y Empleada (interés de la Empleada en CU-09). El CU no indica quién la registró (H-04). | Equipo | Observación H-04. |
| ¿Y si el disparo por tiempo no ocurre o se repite? | No hay disparo: la alerta se calcula cada vez que se abre el panel (D-02), así que no se duplica ni se pierde. | Gerente | REQ-F-12. |
