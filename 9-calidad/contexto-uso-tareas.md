**PLANTILLA PARA DILIGENCIAR · UNIDAD 6 · SESIÓN 1 DE 5**

**Ingeniería de Requisitos**

**Contexto de uso, análisis de tareas y mapa de recorrido — SIGCortinas**

> **Nota de alcance y uso de IA.** Códigos de fuente: **E1** = entrevista a Milena Bermúdez, 28/09/2026; **AT1** = `Kick - off.md` (18/09/2026) y `acta-constitucion.md` (25/09/2026); **CU-nn** = caso de uso correspondiente. No hay observación directa (O), quejas o registros (Q) ni datos de uso (A) para SIGCortinas — el sistema todavía no existe y nadie del equipo ha hecho una visita de observación al local; se marca como limitación de esta entrega, no se rellena con supuestos disfrazados de hechos.

## A. Ficha de contexto de uso

Sistema y pantallas cubiertas: **SIGCortinas — módulos de pedidos/pagos, agenda/visitas, inventario e historial/garantías** (ver `dcu-01-contexto.puml` a `dcu-02d-historial-garantias.puml`)
Versión y fecha: **v1.0 · 22/11/2026**

| Dimensión | Descripción | Fuente(s) |
|---|---|---|
| **Tipos de usuario** | Empleada que atiende en el mostrador, vende, confecciona y agenda citas (E1); Gerente que administra compras, ventas, inventario y garantías (AT1); Técnico que ejecuta instalaciones en campo y consultaría su agenda desde el celular (supuesto, basado en `srs-SIGcortinas.md` §2.1 — sin entrevista directa). | E1, AT1, supuesto (Técnico) |
| **Tareas principales** | (1) Registrar un pedido nuevo (CU-01N); (2) Agendar y consultar visitas de medición/instalación (CU-02, CU-03); (3) Consultar existencias o el historial de un cliente (CU-06, CU-08). | CU-01N, CU-02, CU-03, CU-06, CU-08 |
| **Equipo (aparatos, navegador, conexión)** | Gerente y Empleada: computador de escritorio o portátil existente en el local, navegador web (`srs-SIGcortinas.md` §2.1). Técnico: navegador web del celular, sin app nativa (`srs-SIGcortinas.md` §2.1; `acta-constitucion.md`, "Fuera de esta fase: aplicación móvil nativa"). Conexión a Internet del local, **supuesta** estable (`acta-constitucion.md`, Supuestos). | `srs-SIGcortinas.md`, `acta-constitucion.md` |
| **Entorno físico** | Local principal, Barrio Santa Inés, Tunja; mostrador de atención al cliente; visitas de medición/instalación en domicilios o fincas de clientes (CU-02, extensión 4a: finca a más o menos de 30 min). | `acta-constitucion.md`; `CU-02.md` |
| **Entorno social y organizacional** | Equipo de tres personas (Gerente, Empleada, Técnico) sin áreas separadas; la Empleada "hace de todo" (coser, vender, atender) y reparte su tiempo entre esas tareas durante la jornada (E1, hallazgo 1). | E1 |
| **Restricciones y normas** | Horario de atención 9 am a 6 pm (E1, hallazgo 1); Ley 1581 de 2012 (datos personales) y Ley 1480 de 2011 (garantías) aplican al registro de clientes y pedidos. | E1; `matriz-aplicabilidad__.md`, filas 13-14 |
| **Supuestos y dudas (con responsable)** | (a) **Supuesto**: el Técnico tiene datos móviles suficientes para consultar su agenda en campo — sin confirmar. Responsable: equipo de desarrollo (acción AM-01 de `autoevaluacion-capacidad.md`). (b) **Duda**: "¿Con qué equipos e internet cuenta el local?" (E1, duda pendiente 6). Responsable: Gerente. | E1; inferencia del equipo |

## B. Análisis de tareas

### Tarea 1

Objetivo del usuario: **Dejar constancia completa del pedido de un cliente, sin perder ningún dato.**
Flujo (F-nn): **F-01** Persona: **PER-01**

| N.º y tarea (verbo de usuario) | Pasos (1.1, 1.2...) | Frecuencia | Criticidad (qué pasa si falla) | Cómo se hace hoy | Problemas observados (con fuente) | Medida candidata |
|---|---|---|---|---|---|---|
| **1. Registrar un pedido nuevo** | 1.1 Preguntar y anotar nombre y teléfono del cliente; 1.2 Preguntar el tipo de pedido y tomar las medidas; 1.3 Calcular y anotar el abono inicial (mitad del total). | Varias veces al día: "en un buen día hace 4-5 instalaciones" (E1, hallazgo 8). | Alta: un dato faltante o mal anotado puede dejar el pedido incompleto, o hacer que el Técnico llegue sin saber qué hacer (E1, hallazgo 4). | En un cuaderno, con esfero y memoria (E1, hallazgo 1 y 9). | "Alguna vez se le olvida anotar" un dato (E1, hallazgo 1); "si las medidas no coinciden, la falla es del Técnico y la empresa asume el costo" (E1, hallazgo 4). | % de pedidos registrados sin omitir ningún campo obligatorio en el primer intento. |

### Tarea 2

Objetivo del usuario: **Acordar una fecha y hora de visita sin que se cruce con otra cita del Técnico.**
Flujo (F-nn): **F-02** Persona: **PER-01**

| N.º y tarea (verbo de usuario) | Pasos (1.1, 1.2...) | Frecuencia | Criticidad (qué pasa si falla) | Cómo se hace hoy | Problemas observados (con fuente) | Medida candidata |
|---|---|---|---|---|---|---|
| **2. Agendar una visita de medición o instalación** | 2.1 Preguntar el tipo de visita y la fecha/hora que el cliente prefiere; 2.2 Revisar si el Técnico está libre ese día; 2.3 Confirmar la cita con el cliente. | Variable por semana: "10, 8 y 5" visitas según el mes, sin precisar qué se cuenta exactamente (E1, hallazgo 8 y duda pendiente 4). | Alta: un cruce de horario hace que el Técnico no pueda cumplir una de las dos citas, o que el cliente espere en vano. | Revisando la agenda del cuaderno, distinta de la de la Gerente (E1, hallazgo 2). | "La Gerente y ella llevan agendas diferentes" (E1, hallazgo 2); "las citas se aplazan por disponibilidad del cliente" (E1, hallazgo 3). | % de citas agendadas sin ningún cruce de horario detectado después de confirmarlas. |

### Tarea 3

Objetivo del usuario: **Saber si hay un producto disponible, o qué compró antes un cliente, sin calcular "a ojo".**
Flujo (F-nn): **F-03** Persona: **PER-01 y PER-02**

| N.º y tarea (verbo de usuario) | Pasos (1.1, 1.2...) | Frecuencia | Criticidad (qué pasa si falla) | Cómo se hace hoy | Problemas observados (con fuente) | Medida candidata |
|---|---|---|---|---|---|---|
| **3. Consultar existencias o el historial de un cliente** | 3.1 Recordar o preguntar el nombre/teléfono del cliente, o el nombre del producto; 3.2 Buscar en el cuaderno o en el Excel; 3.3 Confirmar al cliente la respuesta. | Frecuente, sin número exacto registrado (E1, duda pendiente 4, sin responder). | Alta: el acta de constitución exige encontrar una venta pasada o una existencia en menos de 1 minuto (`acta-constitucion.md`, Criterios de éxito). | Con el Excel de la Gerente, que "solo sirve para sumar y no tiene buscador" (E1, duda pendiente 5). | Sin buscador en el Excel; cálculo de stock "a ojo" (`Árbol de Metas KAOS.md`, G2.2). | Tiempo en segundos desde que se ingresa el criterio de búsqueda hasta que se muestra el resultado. |

## C. Mapa de recorrido AS-IS de la persona primaria

Persona: **PER-01** Nombre: **Marcela (representa a Milena Bermúdez)** Meta: **Registrar el pedido de un cliente y agendarle la visita sin perder ningún dato ni cruzar horarios con el Técnico.**

| | Etapa 1 | Etapa 2 | Etapa 3 | Etapa 4 | Etapa 5 | Etapa 6 |
|---|---|---|---|---|---|---|
| **Nombre de la etapa** | El cliente llega al mostrador | Toma los datos del pedido | Calcula el abono inicial | Busca una fecha para la visita | Confirma la cita con el cliente | Vuelve a lo que estaba haciendo |
| **Qué hace (con datos)** | Deja lo que estaba cosiendo o planchando para atender (E1, hallazgo 1). | Pregunta nombre, teléfono, tipo de pedido y medidas, y las anota en el cuaderno (E1). | Calcula a mano la mitad del total acordado como abono (E1, hallazgo 6). | Revisa su propio cuaderno de agenda, sin ver la agenda de la Gerente (E1, hallazgo 2). | Le da al cliente una fecha, sin haber verificado con el Técnico si está libre ese día (inferido de E1, hallazgo 2). | Retoma la tarea que tenía antes de atender (E1, hallazgo 1). |
| **Cómo se siente (una palabra)** | Interrumpida | Concentrada | Insegura | Insegura | Esperanzada | Aliviada (si no olvidó nada) |
| **Punto de dolor (DOL-nn y fuente)** | DOL-07 (inferido de E1, hallazgo 1): atiende mientras hace otra tarea manual, sin un momento dedicado solo al registro. | DOL-01 (E1, hallazgo 1): "alguna vez se le olvida anotar" un dato. | DOL-08 (inferido de E1, hallazgo 6 y `CU-01N.md`, extensión 6b): el cálculo del abono se hace a mano, con riesgo de error. | DOL-02 (E1, hallazgo 2): "la Gerente y ella llevan agendas diferentes". | DOL-09 (inferido de E1, hallazgo 2 y `CU-02.md`, extensión 6a): puede confirmarse una cita que luego resulta cruzada con otra del Técnico. | DOL-03 (E1, hallazgo 9): "el celular no le ayuda"; sus herramientas son "cuaderno, esfero y memoria". |
| **Oportunidad y requisito o criterio** | Interfaz de captura rápida que no le quite tiempo de atención (REQ-NF-04, REQ-NF-07.1). | Campos obligatorios con validación (REQ-F-04a, ya existente). | Validación automática del abono inicial (REQ-F-04b, ya existente). | Agenda compartida entre Gerente, Empleada y Técnico (HU-02, CU-02). | Verificación automática de cruces al confirmar (CU-02, paso 6; REQ-F-01a). | Interfaz simple, sin entrenamiento previo (REQ-NF-04, REQ-NF-07.1 — ver `requisitos-usabilidad-accesibilidad.md`). |

---
