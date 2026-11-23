# Glosario y componentes lógicos · SIGCortinas · v1.0 (21/11/2026)

Nombres exactos que usan los diagramas de secuencia.

## 1. Actores y límite del sistema
| Término | Definición | Fuente |
|---|---|---|
| **Empleada** | Atiende al cliente, vende, agenda y cobra. | ACT-01 |
| **Gerente** | Administra el negocio; valida; controla garantías e inventario. | ACT-02 |
| **Técnico** | Ejecuta mediciones e instalaciones. Se comunica de forma presencial. | ACT-03 |
| **Sistema SIGCortinas** | El sistema tratado como caja negra en el nivel 1. | DCU-01 |
| **Portal de la fábrica** | Sistema externo donde se piden productos y se tramitan garantías. **Sin integración**: no es participante de los diagramas. | Acta §2, CU-09 |
| Cliente | Interesado, no actor: no usa el sistema. | DCU-01 |

## 2. Términos del negocio
| Término | Definición | Fuente |
|---|---|---|
| **Cita** (visita) | Compromiso de medición o instalación con cliente, fecha, hora, dirección, duración y Técnico. | CU-02 |
| **Tipo de visita** | «Medición» o «instalación». | CU-02 |
| **Estado de la cita** | Programada · Realizada · No realizada · Cancelada. | CU-02, 04, 10 |
| **Agenda compartida** | Lista única de citas que ven Gerente, Empleada y Técnico. | CU-02 |
| **Cruce** | Dos citas del mismo Técnico con horarios superpuestos. | WinWin |
| **Franja libre** | Horario del Técnico sin citas. | CU-02 6a |
| **Pedido** | Venta registrada con cliente, tipo, medidas, abono y estado («Pendiente», «Pagado»). | CU-01N |
| **Abono inicial** | Primera mitad del total acordado. Regla de 50 %: REQ-F-04b. | CU-01N |
| **Saldo** | Total del pedido menos los pagos registrados. | CU-05 |
| **Artículo** | Producto o tela del catálogo, con existencia y unidad (rollos, metros, unidades). | CU-06, 07 |
| **Garantía** | Artículo de un pedido enviado a la fábrica por falla. | CU-09 |
| **Estado «En fábrica»** | Estado de la garantía desde su registro. | CU-09 |
| **Referencia del caso** | Código que da el portal de la fábrica; la Gerente lo digita. | CU-09 |
| **Plazo de espera** | 10 a 12 días desde el envío. La alerta aparece cuando los días transcurridos superan este plazo. | Acta, CU-03, CU-09 |
| **Días transcurridos** | Días desde la fecha de envío a la fábrica hasta hoy. | CU-09 p8 |
| **Alerta de plazo excedido** | Marca que muestra una garantía cuyos días transcurridos superan el plazo. | CU-03 2c |
| **Panel principal** | Pantalla inicial con actividades del día y alertas. | Acta §2 |
| **Aviso** | Registro en el sistema de un cambio de agenda dirigido al Técnico y/o la Gerente. El sistema **no** lo envía por ningún canal externo; la entrega al Técnico es presencial (decisión D-01). | CU-02 p8, CU-04 p8 |

## 3. Componentes lógicos (solo nivel 2)
Máximo seis por diagrama. Cada uno es una responsabilidad del negocio, no una clase ni un módulo.

| Componente | Responsabilidad en una frase | Casos |
|---|---|---|
| **Registro de clientes** | Sabe quiénes son los clientes y los busca por teléfono. | CU-02 |
| **Registro de pedidos** | Guarda pedidos y artículos y sabe a qué pedido pertenece cada artículo. | CU-09 |
| **Agenda** | Guarda las citas, detecta cruces y propone franjas libres. | CU-02 |
| **Seguimiento de garantías** | Guarda garantías, cuenta los días transcurridos y decide cuándo se excede el plazo. | CU-09 |
| **Avisos** | Guarda y muestra a cada rol los avisos que le corresponden. | CU-02, 09 |

Prueba de supresión: quitar cualquiera cambia al menos un requisito de `matriz-trazabilidad.md`. No hay componente «Reloj»: la alerta se evalúa al abrir el panel (decisión D-02).
