**PLANTILLA DE TRAZABILIDAD · UNIDAD 4 · SESIÓN 3 DE 5**

**Ingeniería de Requisitos**

**Matriz de trazabilidad NI → meta → historia → requisito → verificación — SIGCortinas**

| Proyecto | Equipo | Fecha | Revisó (otro integrante) |
|---|---|---|---|
| SIGCortinas | Miguel Antonio Gómez Guío, Edward Steven Rocha Torres, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui | 15/11/2026 | Por asignar — pendiente |

## 1. Matriz principal

Trazabilidad completa de los **13 requisitos** especificados en `srs-sigcortinas.md`. Códigos de verificación: CP = caso de prueba · IN = acta de inspección · AN = informe de análisis.

| Req. | Enunciado corto | NI | Meta (G) | HU | Prioridad | Método · evidencia | CU (U5) | Pantalla (U6) | Estado | Observación de la revisión |
|---|---|---|---|---|---|---|---|---|---|---|
| **REQ-F-01a** | Agendar visita sin cruce de horario | NI-02 | G1.1 | HU-02 | Must | Prueba · CP-001 | CU-02 | — | Propuesto | Con ficha 29148 detallada; pendiente firma Gerente |
| **REQ-F-02** | Mostrar actividades del día en el panel | NI-02 (s) | G1.1 | HU-01 | Must | Prueba · CP-002 | CU-03 | — | Propuesto | Con ficha 29148 detallada; pendiente firma Gerente |
| **REQ-F-03** | Reprogramar o cancelar cita | NI-03 | G1.2 | — | Must | Prueba · CP-003 | CU-04 | — | Propuesto | Con ficha 29148 detallada; pendiente firma Gerente |
| **REQ-F-04a** | Rechazar pedido con campos faltantes | NI-01 | G2.1 | — | Must | Prueba · CP-007 | CU-01N | — | Propuesto | Prioridad heredada de CU-01N (`SIGCortinas-backlog-MoSCoW.md`) |
| **REQ-F-04b** | Rechazar abono inicial inválido | NI-06 | G2.1 | — | Must | Prueba · CP-004 | CU-01N | — | Propuesto | Con ficha 29148 detallada; regla del 50 % sin confirmar (D-02) |
| **REQ-F-06** | Consultar existencia de un artículo | NI-08 | G2.2 | — | Must | Prueba · CP-005 | CU-06 | — | Propuesto | Con ficha 29148 detallada; pendiente firma Gerente |
| **REQ-NF-01** | Tiempo de respuesta de búsqueda < 60 s | NI-09 | G3.1 | — | Must | Análisis · AN-001 | CU-08 | — | Propuesto | Fila propia en `SIGCortinas-backlog-MoSCoW.md` (criterio de éxito del acta) |
| **REQ-NF-02** | Control de acceso por rol | NI-11 | — | — | Must | Inspección + Prueba · IN-001/CP-006 | — | — | Propuesto | Origen legal directo (D-03); con ficha 29148 detallada |
| **REQ-F-01b** | Observaciones del trabajo al agendar | NI-04 | G1 | — | Must | Prueba · CP-008 | CU-02 | — | Propuesto | Prioridad heredada de HU-02/CU-02; cubre NI-04 |
| **REQ-F-01c** | Duración estimada de la visita | NI-07 | G1.1/G1.2 | — | Must | Prueba · CP-009 | CU-02 | — | Propuesto | Prioridad heredada de HU-02/CU-02; cubre NI-07 |
| **REQ-F-02a** | Señalar citas sin confirmación previa | NI-05 | G1.1 | HU-01 (s) | Must | Prueba · CP-010 | CU-03 | — | Propuesto | Prioridad heredada de HU-01/CU-03; cubre NI-05 (confirmación) |
| **REQ-F-10** | Registrar garantía y calcular plazo | NI-10 | G3.2 | — | Must | Prueba · CP-011 | CU-09 | — | Propuesto | Prioridad heredada de CU-09; cubre NI-10 |
| **REQ-F-11** | Registrar resultado de visita y validar satisfacción | NI-05 (s) | G1 (G1.1) | — | **Could** | Prueba · CP-012 | CU-10 | — | Propuesto | Prioridad **Could** heredada de CU-10; cubre NI-05 (cierre de visita) |

## 2. Cobertura por necesidad (hacia adelante)

Cobertura de las 11 necesidades de los interesados (`strs-sigcortinas.md`).

| NI | Interesado | Requisitos que la cubren | Prioridad más alta | Diagnóstico |
|---|---|---|---|---|
| NI-01 | Empleada | REQ-F-04a | Must | **Cobertura débil** — cubierta por un solo requisito funcional |
| NI-02 | Empleada / Gerente | REQ-F-01a, REQ-F-02 (s) | Must | Cubierta |
| NI-03 | Empleada / Cliente | REQ-F-03 | Must | Cubierta |
| NI-04 | Empleada / Técnico | REQ-F-01b | Must | **Cobertura débil** — cubierta por un solo requisito; pendiente validar con Técnico (D-05) |
| NI-05 | Empleada / Cliente | REQ-F-02a (Must), REQ-F-11 (Could) | Must | **Cobertura parcial en prioridad** — confirmación previa es Must, encuesta de satisfacción es Could |
| NI-06 | Gerente | REQ-F-04b | Must | Cubierta |
| NI-07 | Gerente / Empleada | REQ-F-01c | Must | **Cobertura débil** — cubierta por un solo requisito; regla de distancia a finca pendiente de confirmación con Gerente |
| NI-08 | Gerente | REQ-F-06 | Must | Cubierta |
| NI-09 | Gerente | REQ-NF-01 | Must | **Cobertura débil** — cubierta por un solo requisito no funcional |
| NI-10 | Gerente | REQ-F-10 | Must | Cubierta |
| NI-11 | Gerente (clientes) | REQ-NF-02 | Must | **Cobertura débil** — cubierta por un solo requisito transversal |

## 3. Registro de decisiones de trazabilidad y alcance

| ID | Caso | Opciones consideradas | Decisión y razón | Aprobó (interesado) | Fecha | Efecto en la matriz y en el backlog |
|---|---|---|---|---|---|---|
| **D-01** | Asignación de prioridad MoSCoW a REQ-F-04a y REQ-NF-01 | (a) Dejarlos sin prioridad hasta planeación; (b) homologar REQ-F-04a con CU-01N (Must) y asignar fila propia Must (3 pts) a REQ-NF-01 según criterio de éxito del acta; (c) excluirlos | **(b)** — REQ-F-04a hereda Must de CU-01N y REQ-NF-01 recibe fila propia Must (3 pts). El Must total sube a 66,04 %, registrado como alerta de capacidad | Decisión del equipo (pendiente revisión de Vicky Beltrán) | 15/11/2026 | `SIGCortinas-backlog-MoSCoW.md` incorpora REQ-NF-01; REQ-F-04a hereda prioridad |
| **D-02** | Regla comercial del abono inicial exacto del 50 % en REQ-F-04b | (a) Mantener la regla del 50 % redondeado al peso superior marcada como pendiente de confirmación; (b) retirar el requisito; (c) eliminar el valor numérico perdiendo verificabilidad | **(a)** — se conserva el umbral exacto del 50 % para garantizar la verificabilidad del requisito, dejando explícito que su ratificación corresponde a la Gerente | Sin cerrar a propósito (requiere confirmación comercial de Vicky Beltrán) | Pendiente | Si la Gerente ajusta el porcentaje, se actualiza el valor en `srs-sigcortinas.md` §1.3 y Ficha 4 |
| **D-03** | Trazabilidad de REQ-NF-02 sin meta KAOS ni CU propio | (a) Crear una meta artificial en el árbol KAOS; (b) trazar directamente a NI-11 y a la Ley 1581 de 2012 (`matriz-aplicabilidad__.md`); (c) eliminar el requisito | **(b)** — el mandato legal de la Ley 1581 de 2012 justifica por sí mismo el requisito y su prioridad Must (5 pts), derivando los permisos específicos de los casos de uso (`CU-01N` a `CU-10`) | Decisión del equipo (pendiente revisión de Vicky Beltrán) | 15/11/2026 | `SIGCortinas-backlog-MoSCoW.md` incorpora fila propia para REQ-NF-02 |
| **D-04** | Cobertura de NI-04, NI-05, NI-07 y NI-10 | (a) Incluir los requisitos REQ-F-01b, REQ-F-01c, REQ-F-02a, REQ-F-10 y REQ-F-11 en el SRS; (b) dejar las NI sin requisito; (c) declararlas fuera de alcance | **(a)** — los cinco requisitos quedan incorporados en `srs-sigcortinas.md` y heredan sus prioridades de sus respectivos casos de uso (`CU-02`, `CU-03`, `CU-09` como Must; `CU-10` como Could) | Decisión del equipo | 15/11/2026 | Cobertura completa de las 11 NI en la matriz sin añadir filas extra al backlog |
| **D-05** | Origen inferido de NI-04 y NI-05 (reportadas por la Empleada, sin entrevista directa al Técnico) | (a) Posponer los requisitos hasta entrevistar al Técnico; (b) especificarlos marcando el origen inferido desde la entrevista a Milena Bermúdez (hallazgos 4 y 5); (c) descartarlos | **(b)** — se mantienen respaldados por la evidencia de la entrevista realizada el 28/09/2026 y se deja abierta la validación directa con el Técnico | Pendiente entrevista con el Técnico | Según disponibilidad del equipo | Si la entrevista al Técnico modifica el flujo, se ajustan REQ-F-01b, REQ-F-02a y REQ-F-11 |
| **D-06** | Diligenciamiento de las columnas CU (U5) y Pantalla (U6) | (a) Dejar ambas vacías hasta las Unidades 5 y 6; (b) registrar los casos de uso ya documentados (`CU-01N` a `CU-10`) y dejar vacía la columna Pantalla | **(b)** — se vinculan los casos de uso existentes en el repositorio para mantener la trazabilidad completa y se reserva la columna Pantalla para la etapa de diseño de interfaz | No aplica | 15/11/2026 | Trazabilidad explícita hacia los casos de uso en la matriz principal |

*Se almacena en `08-requisitos-29148/matriz-trazabilidad.md`.*
