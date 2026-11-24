**PLANTILLA PARA DILIGENCIAR · UNIDAD 6 · SESIÓN 2 DE 5**

**Ingeniería de Requisitos**

**Matriz de trazabilidad CU, pantalla, rol, requisito e historia — SIGCortinas**

> **Nota de alcance.** Construida desde `03-especificacion/casos-de-uso/` (CU-01N a CU-10), `srs-SIGcortinas.md`, `SIGCortinas-backlog-MoSCoW.md` y `ficha-inventario-pantalla.md` (este mismo paquete de entrega), no de memoria. Clasificación usada: **a** = persona con interfaz, **b** = sistema o Planificador, **c** = actor secundario. **Hoy no hay ningún caso de uso de tipo b ni c en el catálogo de SIGCortinas**: los 10 CU son todos tipo "a" (un rol humano con objetivo), y la fábrica/proveedor es una precondición externa en CU-07 y CU-09, no un actor que use pantallas de SIGCortinas. Se deja constancia de esto como información, no como hueco.

| Proyecto | Equipo | Versión de la matriz | Fecha | Revisó (otro integrante) |
|---|---|---|---|---|
| SIGCortinas | Miguel Antonio Gómez Guío, Edward Steven Rocha Torres, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui | v0.1 | 21/11/2026 | Otro integrante del equipo |

## 1. Dirección A · Del caso de uso a la pantalla

| CU | Caso de uso · actor | a, b o c | Pantallas y mensajes | Rol | Requisitos (RF, RNF) | Historia | Chequeo A | Nota o hueco |
|---|---|---|---|---|---|---|---|---|
| **(transversal)** | Control de acceso · todos los roles | a | P-01 | Gerente, Empleada, Técnico | REQ-NF-02 | — | justificado | Sin CU propio: es transversal, igual que el P-00 del ejemplo de la guía. |
| **CU-01N** | Registrar nueva venta o pedido · Empleada | a | P-03 | Empleada | REQ-F-04a, REQ-F-04b; (REQ-F-05 pendiente) | — | completo (parcial en calidad) | REQ-F-05 (flujo completo) sin detallar todavía: ver H-01. |
| **CU-02** | Agendar visita de medición o instalación · Empleada | a | P-04; M-01 | Empleada (Técnico recibe M-01) | REQ-F-01a, REQ-F-01b, REQ-F-01c; (REQ-F-12 pendiente) | HU-02 | completo (parcial en calidad) | REQ-F-12 (flujo completo) sin detallar: ver H-05. |
| **CU-03** | Consultar las actividades programadas del día · Gerente | a | P-02; P-05 (detalle) | Gerente, Empleada, Técnico | REQ-F-02, REQ-F-02a | HU-01 | completo | — |
| **CU-04** | Reprogramar o cancelar una cita · Empleada | a | Sección dentro de P-05; M-02 | Empleada (Técnico y Gerente reciben M-02) | REQ-F-03 | — | completo | Decisión de granularidad (B4): no es pantalla aparte, vive dentro de la ficha de P-05. |
| **CU-05** | Registrar el pago del saldo de un pedido · Empleada | a | P-07 | Empleada | (REQ-F-07 pendiente) | — | parcial | REQ-F-07 (alcance futuro) sin detallar: ver H-02. |
| **CU-06** | Consultar existencias de telas y productos · Empleada | a | P-08 | Empleada, Gerente | REQ-F-06; REQ-NF-01 (justificado) | — | completo | — |
| **CU-07** | Registrar el ingreso de mercancía al inventario · Gerente | a | P-09 | Gerente | (REQ-F-08 pendiente) | — | parcial | REQ-F-08 (alcance futuro) sin detallar: ver H-03. |
| **CU-08** | Buscar el historial de un cliente y sus pedidos · Gerente | a | P-10 | Gerente, Empleada | REQ-NF-01 (justificado); (REQ-F-09 pendiente) | — | parcial | REQ-F-09 (alcance futuro) sin detallar: ver H-04. |
| **CU-09** | Registrar una garantía enviada a la fábrica · Gerente | a | P-11 | Gerente | REQ-F-10; REQ-NF-03 (justificado) | — | completo | — |
| **CU-10** | Registrar el resultado de una visita · Técnico | a | P-06 | Técnico | REQ-F-11 | — | completo | Prioridad **Could** (backlog MoSCoW): pantalla con menor prioridad que el resto. |

## 2. Dirección B · De la pantalla a los casos de uso y los requisitos

| ID | Pantalla o mensaje | Caso(s) de uso | Requisitos que la justifican | Prioridad | ¿Huérfana o sin requisito? Hallazgo |
|---|---|---|---|---|---|
| **P-01** | Iniciar sesión | (transversal) | REQ-NF-02 | Must | No huérfana: transversal, justificada por el control de acceso. |
| **P-02** | Agenda del día | CU-03 | REQ-F-02, REQ-F-02a | Must | — |
| **P-03** | Nuevo pedido | CU-01N | REQ-F-04a, REQ-F-04b | Must | Pendiente: REQ-F-05 (ver H-01). |
| **P-04** | Agendar visita | CU-02 | REQ-F-01a, REQ-F-01b, REQ-F-01c | Must | Pendiente: REQ-F-12 (ver H-05). |
| **P-05** | Detalle de la visita | CU-03, CU-04 | REQ-F-02, REQ-F-03 | Must | — |
| **P-06** | Registrar resultado | CU-10 | REQ-F-11 | Could | — |
| **P-07** | Registrar pago | CU-05 | (ninguno detallado todavía) | Should | Pendiente: REQ-F-07 (ver H-02). |
| **P-08** | Inventario | CU-06 | REQ-F-06, REQ-NF-01 | Must | — |
| **P-09** | Ingreso de mercancía | CU-07 | (ninguno detallado todavía) | Should | Pendiente: REQ-F-08 (ver H-03). |
| **P-10** | Historial de clientes | CU-08 | REQ-NF-01 | Must | Pendiente: REQ-F-09 (ver H-04). |
| **P-11** | Garantías | CU-09 | REQ-F-10, REQ-NF-03 | Must | — |
| **M-01** | Notificación de nueva visita agendada (correo al Técnico) | CU-02, paso 8 | REQ-F-01a (implícito en la notificación) | Must | — |
| **M-02** | Notificación de cambio o cancelación de cita (correo al Técnico y a la Gerente) | CU-04, paso 8 | REQ-F-03 | Must | — |

## 3. Dirección C · Del requisito a la pantalla

| Requisito | Qué pide (resumido) | Pantalla o mensaje donde se ve | Resultado | Decisión si es hueco |
|---|---|---|---|---|
| REQ-F-01a | Agendar visita sin cruce de horario | P-04 | cubierto | — |
| REQ-F-01b | Observaciones del trabajo al agendar | P-04 | cubierto | — |
| REQ-F-01c | Duración estimada de la visita | P-04 | cubierto | — |
| REQ-F-02 | Mostrar actividades del día en el panel | P-02 | cubierto | — |
| REQ-F-02a | Señalar citas sin confirmación previa | P-02 | cubierto | — |
| REQ-F-03 | Reprogramar o cancelar cita | P-05 (sección) | cubierto | — |
| REQ-F-04a | Rechazar pedido con campos faltantes | P-03 | cubierto | — |
| REQ-F-04b | Rechazar abono inicial inválido | P-03 | cubierto | — |
| **REQ-F-05** | Flujo completo de creación de pedido (alcance futuro) | Ninguna todavía | **hueco** | Apoyarlo provisionalmente en P-03; detallar su ficha y confirmar si necesita pantalla propia en la Unidad 7 (H-01). |
| REQ-F-06 | Consultar existencia de un artículo | P-08 | cubierto | — |
| **REQ-F-07** | Registro de pago de saldo (alcance futuro) | Ninguna todavía | **hueco** | Apoyarlo provisionalmente en P-07; detallar en la Unidad 7 (H-02). |
| **REQ-F-08** | Actualización de entradas/salidas de inventario (alcance futuro) | Ninguna todavía | **hueco** | Apoyarlo provisionalmente en P-09; detallar en la Unidad 7 (H-03). |
| **REQ-F-09** | Consulta histórica detallada de ventas (alcance futuro) | Ninguna todavía | **hueco** | Apoyarlo provisionalmente en P-10; detallar en la Unidad 7 (H-04). |
| REQ-F-10 | Registrar garantía y calcular plazo | P-11 | cubierto | — |
| REQ-F-11 | Registrar resultado de visita y validar satisfacción | P-06 | cubierto | — |
| **REQ-F-12** | Flujo completo de agendamiento (alcance futuro) | Ninguna todavía | **hueco** | Apoyarlo provisionalmente en P-04; detallar en la Unidad 7 (H-05). |
| REQ-NF-01 | Tiempo de respuesta de búsqueda | P-08, P-10 | justificado | No es un elemento visible de interfaz; es un atributo de desempeño que se mide sobre esas pantallas. |
| REQ-NF-02 | Control de acceso por rol | P-01 (y tabla rol-pantalla) | cubierto | — |
| REQ-NF-03 | Conservación de datos de venta y garantía | P-11 (sin elemento visible propio) | justificado | Comportamiento interno de almacenamiento, no un elemento de interfaz. |
| REQ-NF-04 | Capacidad de interacción (captura sin entrenamiento) | Transversal a P-03, P-04 | justificado | Criterio transversal de diseño (Sesión 1 de esta unidad), no una pantalla propia. |
| **REQ-NF-05** | Migración inicial de datos | Ninguna | **hueco** | Decidir en la Sesión 3 si se necesita una pantalla de administración de carga, o si la migración se hace por archivo, fuera de la interfaz de usuario final (H-06). |
| REQ-NF-06 | Disponibilidad y no pérdida de registros | Ninguna (atributo de infraestructura) | justificado | No es un elemento de interfaz. |
| REQ-NF-07.1 a 07.3 | Usabilidad medible (Unidad 6, Sesión 1) | P-03, P-04, P-08/P-10 | cubierto | Misma necesidad que REQ-NF-04 y REQ-NF-01, redactada con la fórmula de seis partes; no crea pantalla nueva. |
| REQ-NF-08, REQ-NF-09 | Accesibilidad y adaptabilidad (Unidad 6, Sesión 1) | Transversal; P-06 (adaptabilidad móvil del Técnico) | justificado | Criterios transversales de diseño para las Sesiones 2 a 4. |

## 4. Tabla rol por pantalla (insumo del menú por rol)

| Rol | P-01 | P-02 | P-03 | P-04 | P-05 | P-06 | P-07 | P-08 | P-09 | P-10 | P-11 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **Gerente** | sí | **inicio** | no | no | sí | no | no | sí | sí | sí | sí |
| **Empleada** | sí | **inicio** | sí | sí | sí | no | sí | sí | no | sí | no |
| **Técnico** | sí | **inicio** (vista filtrada: solo sus visitas) | no | no | sí | sí | no | no | no | no | no |

*Ocultar una opción del menú no es controlar el acceso: la verificación del permiso se exige siempre en el servidor (REQ-NF-02). Qué ve exactamente alguien que tuviera dos roles a la vez no se ha presentado en SIGCortinas (los tres roles son personas distintas); si llegara a pasar, se resuelve con la Gerente antes de implementarlo.*

## 5. Lista de huecos y decisiones

| ID | Hueco | Tipo | Decisión | Responsable | Fecha | Estado |
|---|---|---|---|---|---|---|
| **H-01** | REQ-F-05 sin pantalla detallada | Requisito sin pantalla (alcance futuro) | Apoyarlo provisionalmente en P-03; detallar ficha y pantalla exacta en la Unidad 7 | Miguel Antonio Gómez Guío | Inicio de Unidad 7 | abierto |
| **H-02** | REQ-F-07 sin pantalla detallada | Requisito sin pantalla (alcance futuro) | Apoyarlo provisionalmente en P-07; detallar en la Unidad 7 | Edward Steven Rocha Torres | Inicio de Unidad 7 | abierto |
| **H-03** | REQ-F-08 sin pantalla detallada | Requisito sin pantalla (alcance futuro) | Apoyarlo provisionalmente en P-09; detallar en la Unidad 7 | Rafael Santiago Barriosnuevo Mongui | Inicio de Unidad 7 | abierto |
| **H-04** | REQ-F-09 sin pantalla detallada | Requisito sin pantalla (alcance futuro) | Apoyarlo provisionalmente en P-10; detallar en la Unidad 7 | Juan Miguel Chaparro | Inicio de Unidad 7 | abierto |
| **H-05** | REQ-F-12 sin pantalla detallada | Requisito sin pantalla (alcance futuro) | Apoyarlo provisionalmente en P-04; detallar en la Unidad 7 | Miguel Antonio Gómez Guío | Inicio de Unidad 7 | abierto |
| **H-06** | REQ-NF-05 (migración inicial) sin pantalla ni decisión cerrada | Requisito sin pantalla ni justificación cerrada | Decidir si se necesita una pantalla de administración de carga, o si la migración se hace por archivo fuera de la interfaz | Rafael Santiago Barriosnuevo Mongui | Sesión 3 de la Unidad 6 | abierto |
| **H-07** | Ninguna etiqueta de menú se ha comprobado con usuarios reales (ítem C2 de la lista de verificación) | Nombre/etiqueta sin comprobar | Aplicar prueba de etiquetas con las tres personas reales del proyecto (Gerente, Empleada, Técnico), documentando que no se llega al mínimo de cinco personas por ser un proyecto de tres usuarios reales | Juan Miguel Chaparro | Antes de cerrar la Actividad 2 | abierto |

## 6. Registro de cambios de la matriz

| Versión | Fecha | Qué cambió y por qué | Quién |
|---|---|---|---|
| v0.1 | 21/11/2026 | Primera versión: 11 pantallas, 2 mensajes, 10 CU trazados en las tres direcciones, 7 huecos abiertos. | Miguel Antonio Gómez Guío, Juan Miguel Chaparro (con revisión de otro integrante del equipo) |

---
