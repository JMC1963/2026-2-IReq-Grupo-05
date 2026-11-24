**PLANTILLA PARA DILIGENCIAR · UNIDAD 4 · SESIÓN 5**

**Ingeniería de Requisitos**

**Plan de adopción de estándares del proyecto — SIGCortinas**

> **Nota de alcance y uso de IA.** Entregable de cierre de la Unidad 4; tampoco tiene ID en `Indice_trazabilidad.md`. Se diligencia con el nombre de archivo del Ejemplo resuelto (`10-mejora-adopcion/plan-adopcion-estandares.md`). Sustituye a `declaracion-aplicacion-v0.1.md` de la Sesión 1 como documento vigente de estándares (ese archivo queda como antecedente histórico, no se borra). El primer borrador se generó con asistencia de IA a partir de `matriz-aplicabilidad__.md`, `fuentes.md`, `srs-SIGcortinas.md`, `09-calidad/catalogo-rnf.md` y `10-mejora-adopcion/autoevaluacion-capacidad.md`; cada edición de estándar se cotejó contra `fuentes.md` antes de copiarla aquí (ver la "regla de vigencia" de la sección 2).

| **Proyecto** |
|---|
| SIGCortinas — Sistema de gestión para Cortinas Ambiente Moderno, Tunja, Boyacá. |

| **Elaborado por (integrantes del equipo)** |
|---|
| Miguel Antonio Gómez Guío; Edward Steven Rocha Torres; Juan Miguel Chaparro; Rafael Santiago Barriosnuevo Mongui. |

| **Aprueban (nombre y cargo de quienes tienen autoridad en el proyecto)** |
|---|
| Vicky Beltrán — Gerente y patrocinadora. Responsable técnico del equipo de desarrollo (nombre por confirmar, ver `acta-constitucion.md` §8). **Ambas firmas pendientes** (sección 11): este plan se entrega en v0.9 para revisión entre equipos antes de buscar la aprobación real. |

| **Ubicación en el repositorio** |
|---|
| `10-mejora-adopcion/plan-adopcion-estandares.md` |

**Control de versiones**

| Versión | Fecha | Cambio | Autor |
|---|---|---|---|
| 0.9 | 22/11/2026 | Borrador completo para revisión entre equipos (pendiente de asignación del docente) | Equipo de desarrollo (con asistencia de IA, ver nota de alcance) |

## 1. Propósito y alcance

| **Propósito y alcance del plan** |
|---|
| Este plan fija qué estándares usa SIGCortinas, para qué y con qué adaptaciones, y convierte esas decisiones en reglas de trabajo para la especificación completa de la Unidad 7. Cubre los procesos de elicitación, especificación, priorización, validación y gestión de requisitos de calidad, y los documentos `srs-SIGcortinas.md`, `matriz-trazabilidad (2).md` y `09-calidad/catalogo-rnf.md`. **No cubre** diseño, construcción ni pruebas del software. Es coherente con `acta-constitucion.md`: el objetivo sigue siendo reemplazar el cuaderno y el Excel con agenda, ventas, inventario y garantías validados por la Gerente antes del 24/11/2026 (hito que, según la autoevaluación de esta misma sesión, todavía no se ha cumplido de forma real — ver sección 7). Quedan fuera de esta fase, igual que en el acta: integración con el portal de la fábrica, facturación electrónica, acceso de clientes/proveedor y app móvil nativa del Técnico. |

## 2. Estándares adoptados y adaptaciones

La clasificación (Aplica, Parcial, Referencia, No aplica) es la de `matriz-aplicabilidad__.md` (Sesión 1); las fechas de verificación vienen de `fuentes.md` y se reconfirmaron el 22/11/2026.

| Estándar y edición | Papel en el proyecto | Qué se toma | Adaptación y justificación | Verificado (fecha y fuente) |
|---|---|---|---|---|
| ISO/IEC/IEEE 29148:2018 | Norma principal (Parcial) | Contenido del SRS; atributos del requisito; métodos de verificación (CP, IN, AN); niveles de necesidades y de software | No se elabora BRS/StRS/SyRS por separado: el StRS es un extracto (`strs-necesidades.md`, pendiente — acción AM-02). | F01 · 14/11/2026 (`fuentes.md`) |
| ISO/IEC 25010:2023 | Catálogo de calidad (Parcial) | Las nueve características como lista de chequeo de RNF | Se especifican solo las características relevantes según `matriz-relevancia-calidad.md`; seguridad física (safety) descartada con justificación firmada por el equipo (pendiente de validar con la Gerente). | F05 · 14/11/2026 |
| ISO/IEC/IEEE 12207:2026 | Referencia de proceso (Parcial) | Vocabulario y procesos de definición de necesidades y de requisitos del sistema/software | Solo la fase de requisitos. **Regla de vigencia:** la edición correcta es **2026**, no 2017 — error típico que el propio Ejemplo PQRS cometió al copiar una tabla sin cotejarla con `fuentes.md`; aquí se verificó antes de escribir esta fila. | F03 · 14/11/2026 |
| ISO 9000:2026 / ISO 9001:2026 | Referencia de proceso (Referencia) | La revisión de los requisitos por quien tiene autoridad antes de comprometerse (cláusula 8.2), aplicada en `09-calidad/catalogo-rnf.md` §7 | No se busca certificación del proyecto; el acta de revisión de requisitos de calidad es el registro, hoy **propuesto, no firmado** (ver sección 7). | F07 · 14/11/2026 |
| IEEE Std 1061-1998 | Referencia de método | Metodología para pasar de característica de calidad a métrica, umbral y plan de medición (Sesión 4) | Se usa el método, no se cita como norma vigente (estado "Inactiva-reservada" en IEEE SA). | F09 · 14/11/2026 |
| IEEE Std 830-1998 | Referencia de estructura | Esqueleto de capítulos de `srs-SIGcortinas.md` | Solo estructura, sabiendo que está sustituida; el contenido de cada requisito sigue 29148. | F02 · 14/11/2026 |
| ISO/IEC/IEEE 90003:2018 | Referencia (Referencia) | Guía de lectura de ISO 9001 para software | Nota de inconsistencia conocida: 90003:2018 es guía de la edición 9001:2015, mientras este proyecto adopta como referencia 9001:2026; se usa solo como guía general de lectura, no como validación cruzada de ediciones. | F08 · 14/11/2026 |
| ISO/IEC 29110-5-1-2:2025 | Referencia de proceso para equipos pequeños (Parcial) | Perfil básico: gestión del proyecto y especificación de software | Se usa para solicitudes de cambio y repositorio único (acción AM-04); sin evaluación formal de conformidad. | F12 · 14/11/2026 |
| ISO/IEC 25023:2016 | Referencia de medición (Parcial) | Medición seleccionada para REQ-NF-01 (tiempo de búsqueda) | Se mide lo acordado con la Gerente en el acta, no un catálogo completo de métricas de la norma. | F15 · 14/11/2026 |
| CMMI V3.0 (ISACA, 2023) e ISO/IEC 33001:2015 | Inspiración informal de hábitos (siguen **No aplica** para evaluación formal, decisión de la Sesión 1 sin cambios) | Intención de hábitos de gestión de requisitos (sección 4) y lógica de niveles/atributos para la autoevaluación ligera (`10-mejora-adopcion/autoevaluacion-capacidad.md`) | Sin evaluación formal ni nivel oficial: la autoevaluación de esta sesión lo deja explícito en su nota de alcance. No cambia la decisión "No aplica" de `matriz-aplicabilidad__.md`. | F10, F11 · 14/11/2026 |

| **Estándares considerados y no adoptados (y por qué)** |
|---|
| **ISO/IEC 9126-1:2001** — sustituida por 25010; se usa 25010:2023 directamente. **ISO/IEC/IEEE 15288:2023** — el producto es software sobre infraestructura existente, sin elementos de hardware que especificar; queda solo como Referencia en `matriz-aplicabilidad__.md`. **CMMI V3.0** e **ISO/IEC 33001:2015** — evaluación formal de madurez/capacidad desproporcionada para un equipo de cuatro integrantes y un negocio de un solo local; se conserva únicamente su lógica informal (ver tabla de arriba). |

| **Marco legal aplicable (fuentes de requisitos obligatorias, no adaptables)** |
|---|
| **Ley 1581 de 2012** (protección de datos personales): origina REQ-NF-02 del catálogo de calidad. **Ley 1480 de 2011** (protección al consumidor y garantías): origina REQ-NF-03. Ninguna de las dos se declara "cumplida" solo por citarla: el plazo legal exacto de conservación de evidencia (REQ-NF-03) sigue pendiente de confirmar con asesoría legal o contable, igual que en `srs-SIGcortinas.md`. |

## 3. Estructura del SRS

| **Esqueleto elegido y ubicación** |
|---|
| Esqueleto adaptado de IEEE 830-1998 (histórico, usado solo como estructura — ver sección 2), en `srs-SIGcortinas.md`. |

| **Organización de la sección de requisitos específicos y por qué** |
|---|
| (1) Interfaces externas; (2) requisitos funcionales y no funcionales redactados en EARS, organizados por caso de uso de origen (CU-01N a CU-10) más los requisitos transversales de calidad (REQ-NF-01 a REQ-NF-06); (3) Apéndice B con las reglas de diseño y restricciones técnicas (intervalos de cita, abono inicial, campos obligatorios); (4) "Requisitos de alcance futuro" para lo que CU-01N a CU-10 todavía no detallan por completo. Se organiza por caso de uso y no por característica de calidad (a diferencia de PQRS) porque SIGCortinas tiene pocos requisitos funcionales (10 CU) y conviene mantenerlos junto a su origen. |

| **Estado hoy / qué se completa en la Unidad 7** |
|---|
| Hoy: 14 requisitos detallados (REQ-F-01a, 02, 03, 04a, 04b, 06, F-01b, F-01c, F-02a, F-10, F-11, NF-01, NF-02, NF-03) y 5 de "alcance futuro" sin detallar (REQ-F-05, 07, 08, 09, 12). Unidad 7: completar las fichas de las cinco de alcance futuro, incorporar REQ-NF-04 a REQ-NF-06 de esta sesión (acción AM-05) y añadir las interfaces de usuario que resulten del prototipado de la Unidad 6. |

## 4. Reglas de redacción, atributos y trazabilidad

| **Patrón de enunciado y términos prohibidos** |
|---|
| `[condición EARS: CUANDO / SI...ENTONCES / MIENTRAS / DONDE] + SIGCortinas + deberá + acción + objeto + [restricción]`. Un solo verbo de obligación por requisito; el sujeto es siempre "SIGCortinas"; se prohíben adjetivos sin métrica ("rápido", "seguro", "amigable", "fácil") — regla ya aplicada en `actividad-ears-incose__.md` y en `09-calidad/catalogo-rnf.md`. |

| Atributo obligatorio | Qué contiene en este proyecto |
|---|---|
| **Identificador** | REQ-F-xx(letra) para funcionales, REQ-NF-xx para no funcionales, HU-xx, CU-xx(N) — ver esquema abajo. |
| **Enunciado** | EARS ya aplicado (ver `actividad-ears-incose__.md` para los tres ya reescritos: REQ-F-01a, REQ-F-04a, REQ-F-04b). |
| **Justificación** | Una frase, sin repetir el enunciado (ver fichas Volere). |
| **Fuente o propietario** | CU, HU, NI y/o ley de origen, con el interesado dueño cuando aplica. |
| **Prioridad** | MoSCoW (`SIGCortinas-backlog-MoSCoW.md`), heredada del CU/HU de origen o con fila propia si es transversal. |
| **Método de verificación** | Código reservado, ya en uso en `matriz-trazabilidad (2).md`: **CP** (caso de prueba), **IN** (acta de inspección), **AN** (informe de análisis). |
| **Estado** | Propuesto · revisado · aprobado (acta) · cambiado (solicitud) — hoy, **ningún** requisito del repositorio ha llegado realmente a "aprobado" (todos quedan en "Propuesto", ver sección 7). |
| **Trazas** | NI (StRS), meta G del árbol KAOS, HU y/o CU de origen. |

| **Esquema de identificadores y regla de no reutilización** |
|---|
| HU-01 a HU-02; CU-01N a CU-10; REQ-F-01a a REQ-F-12 (algunos con letra para subdivisiones); REQ-NF-01 a REQ-NF-06; NI-01 a NI-11 (implícitas en la matriz, formalizadas en `strs-necesidades.md`, acción AM-02). Ningún identificador eliminado se reutiliza nunca, regla ya vigente en `SKILL.md` y en el catálogo de calidad. |

| **Dónde vive la matriz de trazabilidad y cuándo se actualiza** |
|---|
| `08-requisitos-29148/matriz-trazabilidad.md`. **Regla a partir de ahora:** se actualiza en el mismo PR que cambia o crea un requisito — regla que **todavía no se ha cumplido** (brecha P4 de la autoevaluación: los REQ-NF-04 a 06 de esta sesión no están incorporados aún; acción AM-05 la cierra). |

| **Hábitos tomados de la intención del área de requisitos de CMMI (uno por línea, con su evidencia)** |
|---|
| 1. Toda necesidad con interesado dueño y fuente citada — parcial, columna "Interesado" de la matriz (ver AM-02 para formalizarlo en un StRS). |
| 2. Restricciones registradas con su origen — `acta-constitucion.md` §3, Supuestos y Restricciones. |
| 3. Toda interfaz externa con responsable del otro lado y conversación registrada — **brecha real**: no hay ninguna conversación documentada con la fábrica/proveedor sobre el formato de la referencia de pedido que usa CU-09 (análogo al supuesto S-03 de GestDoc en el PQRS). |
| 4. Un requisito pasa a "aprobado" solo tras revisión de otro integrante y aceptación del interesado — regla declarada en `SKILL.md`, pero **ningún requisito la ha cumplido todavía realmente** (todos siguen "Propuesto"). |
| 5. Todo cambio a un requisito en línea base entra por issue de solicitud de cambio — no implementado (no hay línea base todavía; acción AM-04). |
| 6. La matriz se actualiza en el mismo PR que el requisito — no cumplido hoy (ver arriba; acción AM-05). |

## 5. Catálogo de requisitos de calidad

La única fuente de los enunciados, umbrales y planes de medición es `09-calidad/catalogo-rnf.md`. Este plan no copia enunciados: solo registra el estado de cada requisito.

| ID | Característica (ISO/IEC 25010:2023) | Criterio medible | Necesidad | Estado |
|---|---|---|---|---|
| REQ-NF-01 | Eficiencia de desempeño | ≤ 60 s en el 100% de las consultas del piloto | Criterio de éxito del acta | **Propuesto** |
| REQ-NF-02 | Seguridad | 100% de los 56 (o equivalente) casos de la matriz de roles | Ley 1581/2012 | **Propuesto, condicionado** — falta construir la matriz completa de roles |
| REQ-NF-03 | Fiabilidad | 100% de pedidos con garantía conservan sus datos íntegros | Ley 1480/2011 | **Propuesto, condicionado** — plazo legal exacto por confirmar |
| REQ-NF-04 | Capacidad de interacción | 8/10 intentos sin ayuda en ≤ 3 min | Entrevista, hallazgo 9 | **Propuesto** — umbral supuesto, por validar con la Empleada |
| REQ-NF-05 | Compatibilidad | ≥ 95% migrado sin redigitación, 0 discrepancias | Supuestos del acta | **Propuesto, condicionado** — falta contar los registros reales |
| REQ-NF-06 | Fiabilidad | ≥ 98% disponibilidad, 0 registros perdidos | G1.1; riesgos del acta | **Propuesto** |

**Ninguno de los seis está "Aprobado"**: la revisión de requisitos de `09-calidad/catalogo-rnf.md` §7 sigue pendiente de realizarse de verdad (acción AM-01). Los umbrales son valores de ejemplo del equipo; en la práctica se negocian con la Gerente, como exige la guía.

## 6. Criterios de revisión

| Qué se revisa | Instrumento | Cuándo | Quién |
|---|---|---|---|
| Cada requisito antes de pasar a "aprobado" | Checklist de 29148 (Sesión 3) | En el PR que lo crea o modifica | Quien revisa el PR (nunca el autor) |
| Requisitos Must antes de una línea base | Inspección formal Fagan (Unidad 3, Sesión 5) | Antes de cada etiqueta de línea base | Moderador rotativo + interesado dueño |
| Cada requisito de calidad | Métrica, umbral y plan de medición (Sesión 4) | Al cambiar un umbral | Edward Steven Rocha Torres, con la Gerente |
| El SRS completo, por versión | Checklist de las nueve características de calidad | Al cerrar cada sección en la Unidad 7 | Miguel Antonio Gómez Guío |
| Conjunto de requisitos antes de comprometerse | Acta de revisión de requisitos firmada (cláusula 8.2) | Antes de iniciar el desarrollo, y antes del hito de validación del 24/11/2026 | Vicky Beltrán y responsable técnico del equipo |
| Este plan | Rúbrica de cuatro criterios entre equipos | En cada versión mayor | Equipo revisor que asigne el docente |

| **Definición de «listo» para un requisito** |
|---|
| Ficha con todos los atributos obligatorios de la sección 4; checklist de 29148 sin observaciones abiertas; traza a una NI, a una meta G y a un HU/CU (o decisión escrita de por qué no); revisado por alguien distinto del autor; si es un RNF, su umbral tiene origen declarado y no sigue marcado "supuesto por confirmar" sin una fecha de validación. |

## 7. Capacidad del proceso: actual, objetivo y acciones

| **Nivel actual según la autoevaluación (con la valoración de cada atributo)** |
|---|
| Autoevaluación v1.0, 22/11/2026 (`10-mejora-adopcion/autoevaluacion-capacidad.md`): realización del proceso en **N** (bloqueada por R4, sin validación real con interesados); gestión de la realización en **N**; gestión de los productos de trabajo en **P**; definición del proceso en **P**; despliegue del proceso en **N**. El proceso **no alcanza de forma consistente el Nivel 1 (Realizado)**. |

| **Nivel objetivo y fecha; cómo se comprobará** |
|---|
| Nivel 1 (Realizado) de forma consistente, al cierre de la Unidad 7. Se comprobará con una nueva autoevaluación, contrastada por el equipo revisor que asigne el docente. El Nivel 2 no se fija como objetivo de esta unidad: sería prematuro mientras R4 (validación real) siga en N. |

| **Acciones de mejora (identificadores de la autoevaluación) y cuáles son condición para el objetivo** |
|---|
| AM-01 a AM-07 de `10-mejora-adopcion/autoevaluacion-capacidad.md` §9. Son condición directa para el objetivo (Nivel 1 consistente): **AM-01** (validación real con Vicky Beltrán y el Técnico, cierra R4), **AM-02** (documento StRS, cierra R1) y **AM-03** (cuestionario aplicado, cierra R2). AM-04 a AM-07 mejoran la gestión de productos y la definición del proceso, pero no son condición estricta para el Nivel 1. |

## 8. Calendario de revisiones del plan

| Revisión | Momento | Qué se revisa |
|---|---|---|
| R1 | 28/11/2026 | Cierre de AM-01 y AM-05; si Vicky Beltrán firmó la revisión de requisitos de calidad |
| R2 | Inicio de la Unidad 6 | Si el prototipado cambia REQ-NF-04 o las interfaces de usuario del SRS |
| R3 | Inicio de la Unidad 7 | Reglas, atributos y criterios de revisión de esta sección antes de escribir el SRS completo |
| R4 | Cierre de la Unidad 7 | Nueva autoevaluación de capacidad (objetivo: Nivel 1 consistente) |
| R5 | Antes de iniciar el desarrollo | Revisión formal firmada por la Gerente (cláusula 8.2), coincidiendo con el hito de validación del acta |
| Extraordinaria | Cuando ocurra | Nueva edición de ISO/IEC/IEEE 29148 (hay un proyecto de revisión activo) o de ISO/IEC 25010; cambio en la Ley 1581 o en la Ley 1480; cambio del plazo de garantía (10-12 días) por parte de la fábrica |

| **Eventos que obligan a una revisión extraordinaria (nueva edición de un estándar, cambio legal...)** |
|---|
| Ver fila "Extraordinaria" de la tabla anterior. |

## 9. Responsables

Asignación tomada de `declaracion-aplicacion-v0.1.md` §7, para no crear una segunda versión de los mismos roles.

| Parte del plan | Responsable (nombre propio) |
|---|---|
| **Dueño del plan y del calendario de revisiones** | Rafael Santiago Barriosnuevo Mongui |
| **Verificación de ediciones y vigencia (`fuentes.md`)** | Juan Miguel Chaparro |
| **SRS, reglas de redacción y matriz de trazabilidad** | Miguel Antonio Gómez Guío |
| **Catálogo de calidad** | Edward Steven Rocha Torres |
| **Comunicación con interesados** | Rafael Santiago Barriosnuevo Mongui |
| **Aprobación del plan** | Vicky Beltrán (Gerente) y responsable técnico del equipo (por confirmar) |

## 10. Insumos para la Unidad 7

| **Qué toma la especificación completa de este plan, y qué acciones de mejora caen dentro de la Unidad 7** |
|---|
| El esqueleto del SRS y su organización por caso de uso (sección 3); la ficha de requisito con sus atributos obligatorios y las reglas de redacción EARS (sección 4); la matriz de trazabilidad única, una vez cerrada la acción AM-05; el estado de cada requisito de calidad (sección 5); la definición de "listo" y los criterios de revisión (sección 6); y las acciones **AM-02, AM-06 y AM-07** como tareas con fecha dentro de la Unidad 7 (AM-01, AM-03, AM-04 y AM-05 se cierran antes, en lo que queda de esta unidad). |

## 11. Aprobación

| **Nombre, cargo, firma y fecha — aprobador 1** |
|---|
| Vicky Beltrán — Gerente y patrocinadora. **Pendiente de firma** — se firma tras incorporar los hallazgos de la revisión entre equipos y tras cerrar la acción AM-01 (validación real). |

| **Nombre, cargo, firma y fecha — aprobador 2** |
|---|
| Responsable técnico del equipo de desarrollo (nombre por confirmar, ver `acta-constitucion.md` §8). **Pendiente de firma.** |

## Anexo. Rúbrica de revisión del plan entre equipos

> **Esta sección se deja sin diligenciar a propósito.** A diferencia de las actas internas del equipo (que sí pueden simularse como ejercicio, siempre marcadas como tal), una revisión entre equipos es un hallazgo real de **otro** equipo del curso: inventarlo aquí sería presentar una aprobación o un hallazgo externo que no ocurrió, lo que la regla transversal de `SKILL.md` prohíbe explícitamente ("nunca presentar un acuerdo, firma o aprobación como real si está pendiente o es una simulación"). Esta sección la diligencia el **equipo revisor que asigne el docente** (Actividad 3 de la guía), con los comentarios publicados como comentarios de línea en el PR real, siguiendo las convenciones de la Unidad 3, Sesión 6 (ubicación, evidencia, criterio, severidad, sin proponer la corrección). El resultado de esa revisión se registra aparte, en `10-mejora-adopcion/revision-recibida.md`. |

| **Equipo revisor, PR revisado, fecha y rutas abiertas como muestra** |
|---|
| Por asignar. |

---
