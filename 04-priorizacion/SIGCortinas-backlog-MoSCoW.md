**BACKLOG DE PRODUCTO (MoSCoW) — SIGCortinas**

> Priorización de requisitos de software para **SIGCortinas**, fundamentada en el acta de constitución, las historias de usuario (`HU-01`, `HU-02`), los casos de uso (`CU-01N` a `CU-10`) y las exigencias legales aplicables (`matriz-aplicabilidad__.md`). Los requisitos que constituyen subdivisiones funcionales de un caso de uso con fila propia heredan directamente su prioridad; los requisitos transversales sin caso de uso de origen cuentan con su propia fila de estimación.

## 1. Prioridad heredada desde casos de uso e historias de usuario

| Requisito | Origen funcional | Prioridad | Justificación |
|---|---|---|---|
| REQ-F-01a | HU-02 / CU-02 (Must) | Must | Subdivisión funcional de CU-02; hereda su prioridad sin requerir fila independiente de alcance. |
| REQ-F-01b | HU-02 / CU-02 (Must) | Must | Subdivisión funcional de CU-02; hereda su prioridad. |
| REQ-F-01c | HU-02 / CU-02 (Must) | Must | Subdivisión funcional de CU-02; hereda su prioridad. |
| REQ-F-02 | HU-01 / CU-03 (Must) | Must | Subdivisión funcional de CU-03; hereda su prioridad. |
| REQ-F-02a | HU-01 / CU-03 (Must) | Must | Subdivisión funcional de CU-03; hereda su prioridad. |
| REQ-F-03 | CU-04 (Must) | Must | Corresponde directamente al flujo de reprogramación y cancelación en CU-04. |
| **REQ-F-04a** | CU-01N (Must) | **Must** | Subdivisión directa de CU-01N; homologa la prioridad en el índice de trazabilidad. |
| REQ-F-04b | CU-01N (Must) | Must | Subdivisión directa de CU-01N; hereda su prioridad. |
| REQ-F-06 | CU-06 (Must) | Must | Corresponde directamente a la consulta de inventario en CU-06. |
| REQ-F-10 | CU-09 (Must) | Must | Corresponde directamente al seguimiento de garantías en CU-09. |
| **REQ-F-11** | CU-10 (**Could**) | **Could** | Corresponde al flujo de CU-10, clasificado como **Could** al contar con contingencia operativa (el Técnico puede comunicar el resultado por el canal telefónico actual). |

## 2. Requisitos transversales con fila propia en el backlog

| Requisito | Categoría | Puntos (ilustrativos) | Justificación |
|---|---|---|---|
| **REQ-NF-01** | Must | 3 | El acta de constitución lo exige como criterio de éxito explícito («la Gerente encuentra una venta pasada o una existencia en menos de 1 minuto»). |
| **REQ-NF-02** | Must | 5 | Exigencia legal derivada de la Ley 1581 de 2012 («Aplica» en `matriz-aplicabilidad__.md`), no negociable por decisión del equipo. |

## 3. Distribución y verificación del límite de esfuerzo

| Categoría | Puntos base (CU/HU) | Puntos transversales | Total puntos | % del esfuerzo |
|---|---|---|---|---|
| Must | 27 | +8 (REQ-NF-01, REQ-NF-02) | 35 | **66,04 %** |
| Should | 13 | 0 | 13 | 24,53 % |
| Could | 5 | 0 (REQ-F-11 incluido en CU-10) | 5 | 9,43 % |
| **Total** | **45** | **+8** | **53** | **100 %** |

**Alerta de capacidad del backlog:** la proporción de elementos **Must** alcanza el **66,04 %**, superando el umbral de referencia del ~60 %. Dado que tanto REQ-NF-01 (criterio de éxito del acta de constitución) como REQ-NF-02 (obligación legal bajo Ley 1581 de 2012) son innegociables, no se degradan artificialmente de categoría.

**Resolución registrada:** el exceso sobre el 60 % queda consignado como alerta formal de capacidad para la reunión de planeación con el equipo y la Gerente, donde deberá definirse si se incrementa la capacidad del equipo, se divide alcance de categorías inferiores o se ajusta el cronograma de entrega.
